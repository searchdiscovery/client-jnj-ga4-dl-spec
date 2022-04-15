# Coupon Print Error

Fire whenever a user encounters an error printing a coupon. 

## Javascript Code
```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'coupon_print_error',
  event_data: {
    coupons: '<coupons>',
    error_message: '<error_message>',
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|coupons|delimited string|required|A delimited string of coupons that the user selected and is now downloading or printing.|couponName1\~couponName2\~couponName3|
|error_message|string|required|The specific error that occurred. If an error message is shown to the user, this should be populated with that text.|Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address|
