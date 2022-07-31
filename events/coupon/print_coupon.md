# Print Coupon

Fire whenever a user attempts to print a coupon.

## Javascript Code

```js
// When:
// User attempts to print a coupon

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'coupon_print',
  event_data: {
    coupons: '<coupons>', //Required | string - delimited (~) | ex. couponName1~couponName2~couponName3	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|coupons|delimited string|required|A delimited string of coupons that the user selected and is now downloading or printing.|couponName1\~couponName2\~couponName3|
