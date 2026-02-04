

# WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Item ID. |  [optional] |
|**name** | [**WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerName**](WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerName.md) |  |  [optional] |
|**taxClass** | **String** | Tax class of fee. |  [optional] |
|**taxStatus** | [**TaxStatusEnum**](#TaxStatusEnum) | Tax status of fee. |  [optional] |
|**total** | **String** | Line total (after discounts). |  [optional] |
|**totalTax** | **String** | Line total tax (after discounts). |  [optional] |
|**taxes** | [**List&lt;WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerTaxesInner&gt;**](WooCommerceWcV3OrdersOrderIdRefundsPostRequestFeeLinesInnerTaxesInner.md) | Line taxes. |  [optional] |
|**metaData** | [**List&lt;WooCommerceWcV3CouponsPostRequestMetaDataInner&gt;**](WooCommerceWcV3CouponsPostRequestMetaDataInner.md) | Meta data. |  [optional] |



## Enum: TaxStatusEnum

| Name | Value |
|---- | -----|
| TAXABLE | &quot;taxable&quot; |
| NONE | &quot;none&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



