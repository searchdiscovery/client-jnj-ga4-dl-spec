# Add Payment Info

Fire whenever a user submits their payment information.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "add_payment_info",
  ecommerce: {
    coupon: "<coupon>",
    currency: "<currency>",
    items: "<items>",
    payment_type: "<payment_type>",
    value: "<value>"
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|coupon|string|recommended|The coupon name/code associated with the event. Event-level and item-level coupon parameters are independent.|`SUMMER_FUN`|`^[A-Za-z0-9_]+$`
|currency|string|recommended|Currency of the items associated with the event, in 3-letter ISO 4217 format.|`USD`|`^[A-Z]{3}$`|3|3|
|items|array of [items](/schemas/item.md)|required|Populate with item objects that represent the product viewed.|`[{item_id: "test"}]`
|payment_type|string|recommended|The chosen method of payment.|`credit_card`|`^[a-z_]+$`
|value|number|recommended|The monetary value of the event.|`7.77`|`^\d\.\d\d$`|||0.00|