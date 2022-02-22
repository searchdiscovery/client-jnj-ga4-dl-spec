# Coupon Rebate Offer

Fire whenever a user is presented with a coupon rebate offer.

## Javascript Code

```js
// When:
// User presented with coupon rebate offer

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'coupon_rebate_offer',
  event_data: {
    coupons: '<coupons>', // REQUIRED | string - delimited (~) | ex. couponName1~couponName2~couponName3	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|coupons|delimited string|required|A delimited string of coupons that the user selected and is now downloading or printing.|couponName1\~couponName2\~couponName3|
