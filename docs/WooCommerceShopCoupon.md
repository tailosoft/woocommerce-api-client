

# WooCommerceShopCoupon


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Unique identifier for the object. |  [optional] |
|**code** | **String** | Coupon code. |  [optional] |
|**amount** | [**WooCommerceWcV3CouponsPostRequestAmount**](WooCommerceWcV3CouponsPostRequestAmount.md) |  |  [optional] |
|**status** | **String** | The status of the coupon. Should always be draft, published, or pending review |  [optional] |
|**dateCreated** | **OffsetDateTime** | The date the coupon was created, in the site&#39;s timezone. |  [optional] |
|**dateCreatedGmt** | **OffsetDateTime** | The date the coupon was created, as GMT. |  [optional] |
|**dateModified** | **OffsetDateTime** | The date the coupon was last modified, in the site&#39;s timezone. |  [optional] |
|**dateModifiedGmt** | **OffsetDateTime** | The date the coupon was last modified, as GMT. |  [optional] |
|**discountType** | [**DiscountTypeEnum**](#DiscountTypeEnum) | Determines the type of discount that will be applied. |  [optional] |
|**description** | **String** | Coupon description. |  [optional] |
|**dateExpires** | **OffsetDateTime** | The date the coupon expires, in the site&#39;s timezone. |  [optional] |
|**dateExpiresGmt** | **OffsetDateTime** | The date the coupon expires, as GMT. |  [optional] |
|**usageCount** | **Integer** | Number of times the coupon has been used already. |  [optional] |
|**individualUse** | **Boolean** | If true, the coupon can only be used individually. Other applied coupons will be removed from the cart. |  [optional] |
|**productIds** | **List&lt;Integer&gt;** | List of product IDs the coupon can be used on. |  [optional] |
|**excludedProductIds** | **List&lt;Integer&gt;** | List of product IDs the coupon cannot be used on. |  [optional] |
|**usageLimit** | **Integer** | How many times the coupon can be used in total. |  [optional] |
|**usageLimitPerUser** | **Integer** | How many times the coupon can be used per customer. |  [optional] |
|**limitUsageToXItems** | **Integer** | Max number of items in the cart the coupon can be applied to. |  [optional] |
|**freeShipping** | **Boolean** | If true and if the free shipping method requires a coupon, this coupon will enable free shipping. |  [optional] |
|**productCategories** | **List&lt;Integer&gt;** | List of category IDs the coupon applies to. |  [optional] |
|**excludedProductCategories** | **List&lt;Integer&gt;** | List of category IDs the coupon does not apply to. |  [optional] |
|**excludeSaleItems** | **Boolean** | If true, this coupon will not be applied to items that have sale prices. |  [optional] |
|**minimumAmount** | [**WooCommerceWcV3CouponsPostRequestMinimumAmount**](WooCommerceWcV3CouponsPostRequestMinimumAmount.md) |  |  [optional] |
|**maximumAmount** | [**WooCommerceWcV3CouponsPostRequestMaximumAmount**](WooCommerceWcV3CouponsPostRequestMaximumAmount.md) |  |  [optional] |
|**emailRestrictions** | **List&lt;String&gt;** | List of email addresses that can use this coupon. |  [optional] |
|**usedBy** | **List&lt;Integer&gt;** | List of user IDs (or guest email addresses) that have used the coupon. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopCouponMetaDataInner&gt;**](WooCommerceShopCouponMetaDataInner.md) | Meta data. |  [optional] |



## Enum: DiscountTypeEnum

| Name | Value |
|---- | -----|
| PERCENT | &quot;percent&quot; |
| FIXED_CART | &quot;fixed_cart&quot; |
| FIXED_PRODUCT | &quot;fixed_product&quot; |
| UNKNOWN_DEFAULT_OPEN_API | &quot;unknown_default_open_api&quot; |



