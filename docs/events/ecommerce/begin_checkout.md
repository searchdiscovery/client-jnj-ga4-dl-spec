# Begin Checkout

Fire whenever a user begins a checkout.

## Javascript Code

```js
// When:
// User begins a checkout

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "begin_checkout",
  ecommerce: {
    coupon: "<coupon>", // recommended | string | ex. SUMMER_FUN | pattern: ^[A-Za-z0-9_]+$
    currency: "<currency>", // recommended | string | ex. USD | pattern: ^[A-Z]{3}$ | min. 3, max. 3
    items: "<items>", // REQUIRED | array | ex. [{item_id: "test"}]	
    value: "<value>" // recommended | number | ex. 7.77 | pattern: ^\d\.\d\d$	 | min. 0.00
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|coupon|string|recommended|The coupon name/code associated with the event. Event-level and item-level coupon parameters are independent.|`SUMMER_FUN`|`^[A-Za-z0-9_]+$`
|currency|string|recommended|Currency of the items associated with the event, in 3-letter ISO 4217 format.|`USD`|`^[A-Z]{3}$`|3|3|
|items|array of [items](/schemas/item.md)|required|Populate with item objects that represent the product viewed.|`[{item_id: "test"}]`
|value|number|recommended|The monetary value of the event.|`7.77`|`^\d\.\d\d$`|||0.00|