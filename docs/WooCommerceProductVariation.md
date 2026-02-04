

# WooCommerceProductVariation


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Unique identifier for the resource. |  [optional] |
|**type** | **String** | Product type. |  [optional] |
|**dateCreated** | **OffsetDateTime** | The date the variation was created, in the site&#39;s timezone. |  [optional] |
|**dateModified** | **OffsetDateTime** | The date the variation was last modified, in the site&#39;s timezone. |  [optional] |
|**description** | **String** | Variation description. |  [optional] |
|**permalink** | **URI** | Variation URL. |  [optional] |
|**sku** | **String** | Stock Keeping Unit. |  [optional] |
|**globalUniqueId** | **String** | GTIN, UPC, EAN or ISBN. |  [optional] |
|**price** | **String** | Current variation price. |  [optional] |
|**regularPrice** | **String** | Variation regular price. |  [optional] |
|**salePrice** | **String** | Variation sale price. |  [optional] |
|**dateOnSaleFrom** | **OffsetDateTime** | Start date of sale price, in the site&#39;s timezone. |  [optional] |
|**dateOnSaleFromGmt** | **OffsetDateTime** | Start date of sale price, as GMT. |  [optional] |
|**dateOnSaleTo** | **OffsetDateTime** | End date of sale price, in the site&#39;s timezone. |  [optional] |
|**dateOnSaleToGmt** | **OffsetDateTime** | End date of sale price, in the site&#39;s timezone. |  [optional] |
|**onSale** | **Boolean** | Shows if the variation is on sale. |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Variation status. |  [optional] |
|**purchasable** | **Boolean** | Shows if the variation can be bought. |  [optional] |
|**virtual** | **Boolean** | If the variation is virtual. |  [optional] |
|**downloadable** | **Boolean** | If the variation is downloadable. |  [optional] |
|**downloads** | [**List&lt;WooCommerceWcV3ProductsPostRequestDownloadsInner&gt;**](WooCommerceWcV3ProductsPostRequestDownloadsInner.md) | List of downloadable files. |  [optional] |
|**downloadLimit** | **Integer** | Number of times downloadable files can be downloaded after purchase. |  [optional] |
|**downloadExpiry** | **Integer** | Number of days until access to downloadable files expires. |  [optional] |
|**taxStatus** | [**TaxStatusEnum**](#TaxStatusEnum) | Tax status. |  [optional] |
|**taxClass** | **String** | Tax class. |  [optional] |
|**manageStock** | [**WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock**](WooCommerceWcV3ProductsProductIdVariationsPostRequestManageStock.md) |  |  [optional] |
|**stockQuantity** | **Integer** | Stock quantity. |  [optional] |
|**stockStatus** | [**StockStatusEnum**](#StockStatusEnum) | Controls the stock status of the product. |  [optional] |
|**backorders** | [**BackordersEnum**](#BackordersEnum) | If managing stock, this controls if backorders are allowed. |  [optional] |
|**backordersAllowed** | **Boolean** | Shows if backorders are allowed. |  [optional] |
|**backordered** | **Boolean** | Shows if the variation is on backordered. |  [optional] |
|**lowStockAmount** | **Integer** | Low Stock amount for the variation. |  [optional] |
|**weight** | **String** | Variation weight (lbs). |  [optional] |
|**dimensions** | [**WooCommerceWcV3ProductsProductIdVariationsPostRequestDimensions**](WooCommerceWcV3ProductsProductIdVariationsPostRequestDimensions.md) |  |  [optional] |
|**shippingClass** | **String** | Shipping class slug. |  [optional] |
|**shippingClassId** | **String** | Shipping class ID. |  [optional] |
|**image** | [**WooCommerceProductVariationImage**](WooCommerceProductVariationImage.md) |  |  [optional] |
|**attributes** | [**List&lt;WooCommerceWcV3ProductsPostRequestDefaultAttributesInner&gt;**](WooCommerceWcV3ProductsPostRequestDefaultAttributesInner.md) | List of attributes. |  [optional] |
|**menuOrder** | **Integer** | Menu order, used to custom sort products. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopCouponMetaDataInner&gt;**](WooCommerceShopCouponMetaDataInner.md) | Meta data. |  [optional] |
|**parentId** | **Integer** | Product parent ID. |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| DRAFT | &quot;draft&quot; |
| PENDING | &quot;pending&quot; |
| PRIVATE | &quot;private&quot; |
| PUBLISH | &quot;publish&quot; |
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



