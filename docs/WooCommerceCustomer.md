

# WooCommerceCustomer


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Unique identifier for the resource. |  [optional] |
|**dateCreated** | **OffsetDateTime** | The date the customer was created, in the site&#39;s timezone. |  [optional] |
|**dateCreatedGmt** | **OffsetDateTime** | The date the customer was created, as GMT. |  [optional] |
|**dateModified** | **OffsetDateTime** | The date the customer was last modified, in the site&#39;s timezone. |  [optional] |
|**dateModifiedGmt** | **OffsetDateTime** | The date the customer was last modified, as GMT. |  [optional] |
|**email** | **String** | The email address for the customer. |  [optional] |
|**firstName** | **String** | Customer first name. |  [optional] |
|**lastName** | **String** | Customer last name. |  [optional] |
|**role** | **String** | Customer role. |  [optional] |
|**username** | **String** | Customer login name. |  [optional] |
|**password** | **String** | Customer password. |  [optional] |
|**billing** | [**WooCommerceWcV3CustomersPostRequestBilling**](WooCommerceWcV3CustomersPostRequestBilling.md) |  |  [optional] |
|**shipping** | [**WooCommerceWcV3CustomersPostRequestShipping**](WooCommerceWcV3CustomersPostRequestShipping.md) |  |  [optional] |
|**isPayingCustomer** | **Boolean** | Is the customer a paying customer? |  [optional] |
|**avatarUrl** | **String** | Avatar URL. |  [optional] |
|**metaData** | [**List&lt;WooCommerceShopCouponMetaDataInner&gt;**](WooCommerceShopCouponMetaDataInner.md) | Meta data. |  [optional] |



