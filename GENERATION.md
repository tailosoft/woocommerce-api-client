# OpenAPI Generator Command

This Java client was generated using the OpenAPI Generator Docker image.

## Why we generate this library

There is no official OpenAPI spec for WooCommerce. I opened an issue for that: https://github.com/woocommerce/woocommerce/issues/45733

There is now an extension [WP OpenAPI](https://wordpress.org/plugins/wp-openapi/) that generates an OpenAPI spec. An extension is needed because of how types are defined in WordPress/WooCommerce code, making them only available at runtime (hard to do generation from static code).

We are generating the library ourselves as other libraries seem incomplete.

## Generating woocommerce.json

The `woocommerce.json` OpenAPI specification is generated using a fork of the [wp-openapi](https://github.com/moon0326/wp-openapi) plugin.

We had to make two fixes to this plugin:
1. Fix dateTime format handling
2. Detect collections properly

To generate the spec:

```bash
docker compose -f src/main/docker/wordpress.yml up
```

Then download the file for `/wc/v3` (the latest WooCommerce API) and click on export (Bundled References).

After generating the specification, add the basicAuth security scheme and apply it globally:

```bash
jq '.components.securitySchemes.basicAuth = {"type": "http", "scheme": "basic"} | .security = [{"basicAuth": []}]' \
  woocommerce.json > woocommerce.json.tmp && mv woocommerce.json.tmp woocommerce.json
```

This adds:
- `securitySchemes` under `components` - defines the basicAuth scheme
- `security` at root level - applies authentication to all API operations

Then, make `meta_data[].value` accept any JSON type (string, object, or array) since WooCommerce plugins can store complex objects in metadata:

```bash
jq 'walk(
  if type == "object" and .properties?.value?.type == "string" and .properties?.key?.type == "string" then
    .properties.value = {"description": "Meta value."}
  else .
  end
)' woocommerce.json > woocommerce.json.tmp && mv woocommerce.json.tmp woocommerce.json
```

This removes the `type: string` constraint from `value` fields in metadata objects, allowing plugins like PixelYourSite to store tracking data as JSON objects.

## Command
o
```bash
docker run --rm \
  -v $JSON_PATH/woocommerce.json:/local/woocommerce.json \
  -v $OUTPUT_PARENT_FOLDER/woocommerce-api-java-client:/local/output \
  openapitools/openapi-generator-cli generate \
  -i /local/woocommerce.json \
  -g java \
  -o /local/output \
  --library okhttp-gson \
  --additional-properties=groupId=com.tailosoft,artifactId=woocommerce-api-client,invokerPackage=com.woocommerce,apiPackage=com.woocommerce.api,modelPackage=com.woocommerce.model,dateLibrary=java8,useJakartaEe=false,java8=true,modelNamePrefix=WooCommerce,apiNameSuffix=WooCommerceApi,hideGenerationTimestamp=true,useSingleRequestParameter=true,disallowAdditionalPropertiesIfNotPresent=false,enumUnknownDefaultCase=true

sudo chown -R $USER:$USER $OUTPUT_PARENT_FOLDER/woocommerce-api-java-client/
chmod +x ./gradlew
```

## Options Explained

| Option | Value | Description |
|--------|-------|-------------|
| `-g` | `java` | Generator type |
| `--library` | `okhttp-gson` | OkHttp 4 with Gson serialization. Required to avoid method ambiguity errors when using `useSingleRequestParameter=true` (the `native` library generates ambiguous method overloads) |
| `groupId` | `com.tailosoft` | Maven group ID |
| `artifactId` | `woocommerce-api-client` | Maven artifact ID |
| `invokerPackage` | `com.woocommerce` | Base package for client classes |
| `apiPackage` | `com.woocommerce.api` | Package for API classes |
| `modelPackage` | `com.woocommerce.model` | Package for model classes |
| `dateLibrary` | `java8` | Use Java 8 date/time types |
| `useJakartaEe` | `false` | Use javax namespace (not Jakarta) |
| `java8` | `true` | Enable Java 8 features |
| `modelNamePrefix` | `WooCommerce` | Prefix all model class names |
| `apiNameSuffix` | `WooCommerceApi` | Suffix all API class names |
| `hideGenerationTimestamp` | `true` | Remove generation date from @Generated annotations |
| `useSingleRequestParameter` | `true` | Generate request objects with fluent builders instead of many parameters |
| `disallowAdditionalPropertiesIfNotPresent` | `false` | Allow custom fields in WooCommerce responses |
| `enumUnknownDefaultCase` | `true` | Handle unknown enum values gracefully |

## Requirements

- Java 8+
- Gradle or Maven for building

## Manual changes

After generation, manually fix these files for the code to compile/work correctly:

### 1. `src/main/java/com/woocommerce/model/WooCommerceProductVariation.java`

Remove `= false` from the `manageStock` field initialization:
```java
// Change this:
private WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock manageStock = false;

// To this:
private WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock manageStock;
```

### 2. `src/main/java/com/woocommerce/JSON.java` (in .openapi-generator-ignore)

This file is excluded from regeneration. It contains a fix for WooCommerce date parsing.

WooCommerce returns dates without timezone offsets (e.g., `2026-02-04T06:17:28`), but the default `OffsetDateTimeTypeAdapter` expects ISO-8601 with offset. The fix in `OffsetDateTimeTypeAdapter.read()` checks the string length (19 chars = no offset) and parses accordingly, assuming UTC:

```java
// WooCommerce returns dates without timezone offset (e.g., "2026-02-04T06:17:28")
// which is exactly 19 chars. Dates with offset are longer (Z, +00:00, etc.)
if (date.length() == 19) {
    return LocalDateTime.parse(date, DateTimeFormatter.ISO_LOCAL_DATE_TIME).atOffset(ZoneOffset.UTC);
}
return OffsetDateTime.parse(date, formatter);
```

Required imports added:
```java
import java.time.LocalDateTime;
import java.time.ZoneOffset;
```

## Testing

Once the project compiles, to test it:
```bash
./gradlew publishToMavenLocal
```

## Releasing to Maven Central

Credentials are read from `~/.m2/settings.xml` (the `central` server entry), which expects `CENTRAL_USERNAME` / `CENTRAL_TOKEN` — user tokens generated at https://central.sonatype.com/account (not your Sonatype Jira password). Artifacts are GPG-signed via the `sign-artifacts` profile.

Export the credentials (KeyPass) then run the deploy:
```bash
export CENTRAL_USERNAME=<your-portal-username>
export CENTRAL_TOKEN=<your-portal-token>
mvn clean deploy -Psign-artifacts
```

With `<autoPublish>true</autoPublish>` in the `central-publishing-maven-plugin` config, the release is pushed to Central as soon as validation passes — no manual approval step at https://central.sonatype.com/publishing/deployments. Flip it to `false` if you want a staging step you can inspect first.
