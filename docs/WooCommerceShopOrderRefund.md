

# WooCommerceShopOrderRefund


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Unique identifier for the resource. |  [optional] |
|**parentId** | **Integer** | Parent order ID. |  [optional] |
|**dateCreated** | **OffsetDateTime** | The date the order refund was created, in the site&#39;s timezone. |  [optional] |
|**dateCreatedGmt** | **OffsetDateTime** | The date the order refund was created, as GMT. |  [optional] |
|**amount** | **String** | Refund amount. |  [optional] |
|**reason** | **String** | Reason for refund. |  [optional] |
|**refundedBy** | **Integer** | User ID of user who created the refund. |  [optional] |
|**refundedPayment** | **Boolean** | If the payment was refunded via the API. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopCouponMetaDataInner&gt;**](WooCommerceShopCouponMetaDataInner.md) | Meta data. |  [optional] |
|**lineItems** | [**List&lt;WooCommerceShopOrderRefundLineItemsInner&gt;**](WooCommerceShopOrderRefundLineItemsInner.md) | Line items data. |  [optional] |
|**taxLines** | [**List&lt;WooCommerceShopOrderRefundTaxLinesInner&gt;**](WooCommerceShopOrderRefundTaxLinesInner.md) | Tax lines data. |  [optional] |
|**shippingLines** | [**List&lt;WooCommerceShopOrderRefundShippingLinesInner&gt;**](WooCommerceShopOrderRefundShippingLinesInner.md) | Shipping lines data. |  [optional] |
|**feeLines** | [**List&lt;WooCommerceShopOrderRefundFeeLinesInner&gt;**](WooCommerceShopOrderRefundFeeLinesInner.md) | Fee lines data. |  [optional] |
|**apiRefund** | **Boolean** | When true, the payment gateway API is used to generate the refund. |  [optional] |
|**apiRestock** | **Boolean** | When true, refunded items are restocked. |  [optional] |



