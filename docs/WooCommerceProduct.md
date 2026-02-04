

# WooCommerceProduct


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Unique identifier for the resource. |  [optional] |
|**name** | **String** | Product name. |  [optional] |
|**slug** | **String** | Product slug. |  [optional] |
|**permalink** | **URI** | Product URL. |  [optional] |
|**dateCreated** | **OffsetDateTime** | The date the product was created, in the site&#39;s timezone. |  [optional] |
|**dateCreatedGmt** | **OffsetDateTime** | The date the product was created, as GMT. |  [optional] |
|**dateModified** | **OffsetDateTime** | The date the product was last modified, in the site&#39;s timezone. |  [optional] |
|**dateModifiedGmt** | **OffsetDateTime** | The date the product was last modified, as GMT. |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) | Product type. |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Product status (post status). |  [optional] |
|**featured** | **Boolean** | Featured product. |  [optional] |
|**catalogVisibility** | [**CatalogVisibilityEnum**](#CatalogVisibilityEnum) | Catalog visibility. |  [optional] |
|**description** | **String** | Product description. |  [optional] |
|**shortDescription** | **String** | Product short description. |  [optional] |
|**sku** | **String** | Stock Keeping Unit. |  [optional] |
|**globalUniqueId** | **String** | GTIN, UPC, EAN or ISBN. |  [optional] |
|**price** | **String** | Current product price. |  [optional] |
|**regularPrice** | **String** | Product regular price. |  [optional] |
|**salePrice** | **String** | Product sale price. |  [optional] |
|**dateOnSaleFrom** | **OffsetDateTime** | Start date of sale price, in the site&#39;s timezone. |  [optional] |
|**dateOnSaleFromGmt** | **OffsetDateTime** | Start date of sale price, as GMT. |  [optional] |
|**dateOnSaleTo** | **OffsetDateTime** | End date of sale price, in the site&#39;s timezone. |  [optional] |
|**dateOnSaleToGmt** | **OffsetDateTime** | End date of sale price, in the site&#39;s timezone. |  [optional] |
|**priceHtml** | **String** | Price formatted in HTML. |  [optional] |
|**onSale** | **Boolean** | Shows if the product is on sale. |  [optional] |
|**purchasable** | **Boolean** | Shows if the product can be bought. |  [optional] |
|**totalSales** | **Integer** | Amount of sales. |  [optional] |
|**virtual** | **Boolean** | If the product is virtual. |  [optional] |
|**downloadable** | **Boolean** | If the product is downloadable. |  [optional] |
|**downloads** | [**List&lt;WooCommerceWcV3ProductsPostRequestDownloadsInner&gt;**](WooCommerceWcV3ProductsPostRequestDownloadsInner.md) | List of downloadable files. |  [optional] |
|**downloadLimit** | **Integer** | Number of times downloadable files can be downloaded after purchase. |  [optional] |
|**downloadExpiry** | **Integer** | Number of days until access to downloadable files expires. |  [optional] |
|**externalUrl** | **URI** | Product external URL. Only for external products. |  [optional] |
|**buttonText** | **String** | Product external button text. Only for external products. |  [optional] |
|**taxStatus** | [**TaxStatusEnum**](#TaxStatusEnum) | Tax status. |  [optional] |
|**taxClass** | **String** | Tax class. |  [optional] |
|**manageStock** | **Boolean** | Stock management at product level. |  [optional] |
|**stockQuantity** | **Integer** | Stock quantity. |  [optional] |
|**stockStatus** | [**StockStatusEnum**](#StockStatusEnum) | Controls the stock status of the product. |  [optional] |
|**backorders** | [**BackordersEnum**](#BackordersEnum) | If managing stock, this controls if backorders are allowed. |  [optional] |
|**backordersAllowed** | **Boolean** | Shows if backorders are allowed. |  [optional] |
|**backordered** | **Boolean** | Shows if the product is on backordered. |  [optional] |
|**lowStockAmount** | **Integer** | Low Stock amount for the product. |  [optional] |
|**soldIndividually** | **Boolean** | Allow one item to be bought in a single order. |  [optional] |
|**weight** | **String** | Product weight (lbs). |  [optional] |
|**dimensions** | [**WooCommerceWcV3ProductsPostRequestDimensions**](WooCommerceWcV3ProductsPostRequestDimensions.md) |  |  [optional] |
|**shippingRequired** | **Boolean** | Shows if the product need to be shipped. |  [optional] |
|**shippingTaxable** | **Boolean** | Shows whether or not the product shipping is taxable. |  [optional] |
|**shippingClass** | **String** | Shipping class slug. |  [optional] |
|**shippingClassId** | **String** | Shipping class ID. |  [optional] |
|**reviewsAllowed** | **Boolean** | Allow reviews. |  [optional] |
|**postPassword** | **String** | Post password. |  [optional] |
|**averageRating** | **String** | Reviews average rating. |  [optional] |
|**ratingCount** | **Integer** | Amount of reviews that the product have. |  [optional] |
|**relatedIds** | **List&lt;Integer&gt;** | List of related products IDs. |  [optional] |
|**upsellIds** | **List&lt;Integer&gt;** | List of up-sell products IDs. |  [optional] |
|**crossSellIds** | **List&lt;Integer&gt;** | List of cross-sell products IDs. |  [optional] |
|**parentId** | **Integer** | Product parent ID. |  [optional] |
|**purchaseNote** | **String** | Optional note to send the customer after purchase. |  [optional] |
|**categories** | [**List&lt;WooCommerceWcV3ProductsPostRequestCategoriesInner&gt;**](WooCommerceWcV3ProductsPostRequestCategoriesInner.md) | List of categories. |  [optional] |
|**brands** | [**List&lt;WooCommerceWcV3ProductsPostRequestBrandsInner&gt;**](WooCommerceWcV3ProductsPostRequestBrandsInner.md) | List of brands. |  [optional] |
|**tags** | [**List&lt;WooCommerceWcV3ProductsPostRequestTagsInner&gt;**](WooCommerceWcV3ProductsPostRequestTagsInner.md) | List of tags. |  [optional] |
|**images** | [**List&lt;WooCommerceProductImagesInner&gt;**](WooCommerceProductImagesInner.md) | List of images. |  [optional] |
|**hasOptions** | **Boolean** | Shows if the product needs to be configured before it can be bought. |  [optional] |
|**attributes** | [**List&lt;WooCommerceWcV3ProductsPostRequestAttributesInner&gt;**](WooCommerceWcV3ProductsPostRequestAttributesInner.md) | List of attributes. |  [optional] |
|**defaultAttributes** | [**List&lt;WooCommerceWcV3ProductsPostRequestDefaultAttributesInner&gt;**](WooCommerceWcV3ProductsPostRequestDefaultAttributesInner.md) | Defaults variation attributes. |  [optional] |
|**variations** | **List&lt;Integer&gt;** | List of variations IDs. |  [optional] |
|**groupedProducts** | **List&lt;Integer&gt;** | List of grouped products ID. |  [optional] |
|**menuOrder** | **Integer** | Menu order, used to custom sort products. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopCouponMetaDataInner&gt;**](WooCommerceShopCouponMetaDataInner.md) | Meta data. |  [optional] |
|**permalinkTemplate** | **String** | Permalink template for the product. |  [optional] |
|**generatedSlug** | **String** | Slug automatically generated from the product name. |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| SIMPLE | &quot;simple&quot; |
| GROUPED | &quot;grouped&quot; |
| EXTERNAL | &quot;external&quot; |
| VARIABLE | &quot;variable&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| DRAFT | &quot;draft&quot; |
| PENDING | &quot;pending&quot; |
| PRIVATE | &quot;private&quot; |
| PUBLISH | &quot;publish&quot; |
| FUTURE | &quot;future&quot; |
| AUTO_DRAFT | &quot;auto-draft&quot; |
| TRASH | &quot;trash&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



## Enum: CatalogVisibilityEnum

| Name | Value |
|---- | -----|
| VISIBLE | &quot;visible&quot; |
| CATALOG | &quot;catalog&quot; |
| SEARCH | &quot;search&quot; |
| HIDDEN | &quot;hidden&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



## Enum: TaxStatusEnum

| Name | Value |
|---- | -----|
| TAXABLE | &quot;taxable&quot; |
| SHIPPING | &quot;shipping&quot; |
| NONE | &quot;none&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



## Enum: StockStatusEnum

| Name | Value |
|---- | -----|
| INSTOCK | &quot;instock&quot; |
| OUTOFSTOCK | &quot;outofstock&quot; |
| ONBACKORDER | &quot;onbackorder&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



## Enum: BackordersEnum

| Name | Value |
|---- | -----|
| NO | &quot;no&quot; |
| NOTIFY | &quot;notify&quot; |
| YES | &quot;yes&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



