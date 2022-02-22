# Coupon Rebate Offer

Fire whenever a user is presented with a coupon rebate offer.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'coupon_rebate_offer',
  event_data: {
    identifier: '<identifier>',
    name: '<name>',
    type: '<type>'
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The coupon machine-readable name. This should be a unique value specific to this coupon, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|neutrogena_discount, free_shipping_q421|
|name|string|required|The coupon human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the coupon with. It should be lowercase snake_case.|neutrogena_discount, free_shipping_q421|
|type|string|required|The coupon type. This will act as a filtering mechanism in reporting to enable analysts to view coupon engagement. It can also act as an internal aid in firing additional events if necessary.|discount, promo|
