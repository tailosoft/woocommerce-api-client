# OpenAPI Generator Command

This Java client was generated using the OpenAPI Generator Docker image.

## Generating woocommerce.json

The `woocommerce.json` OpenAPI specification is generated using a fork of the [wp-openapi](https://github.com/moon0326/wp-openapi) plugin.

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

After generation, manually fix this file for the code to compile:

`src/main/java/com/woocommerce/model/WooCommerceProductVariation.java`

Remove `= false` from the `manageStock` field initialization:
```java
// Change this:
private WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock manageStock = false;

// To this:
private WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock manageStock;
```

## Testing

Once the project compiles, to test it:
```bash
./gradlew publishToMavenLocal
```
