

# WooCommerceShopOrderLineItemsInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Item ID. |  [optional] |
|**name** | **String** | Product name. |  [optional] |
|**parentName** | **String** | Parent product name if the product is a variation. |  [optional] |
|**productId** | **String** | Product ID. |  [optional] |
|**variationId** | **Integer** | Variation ID, if applicable. |  [optional] |
|**quantity** | **Integer** | Quantity ordered. |  [optional] |
|**taxClass** | **String** | Tax class of product. |  [optional] |
|**subtotal** | **String** | Line subtotal (before discounts). |  [optional] |
|**subtotalTax** | **String** | Line subtotal tax (before discounts). |  [optional] |
|**total** | **String** | Line total (after discounts). |  [optional] |
|**totalTax** | **String** | Line total tax (after discounts). |  [optional] |
|**taxes** | [**List&lt;WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerTaxesInner&gt;**](WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerTaxesInner.md) | Line taxes. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopOrderLineItemsInnerMetaDataInner&gt;**](WooCommerceShopOrderLineItemsInnerMetaDataInner.md) | Meta data. |  [optional] |
|**sku** | **String** | Product SKU. |  [optional] |
|**globalUniqueId** | **String** | GTIN, UPC, EAN or ISBN. |  [optional] |
|**price** | **BigDecimal** | Product price. |  [optional] |
|**image** | [**WooCommerceWcV3OrdersPostRequestLineItemsInnerImage**](WooCommerceWcV3OrdersPostRequestLineItemsInnerImage.md) |  |  [optional] |



