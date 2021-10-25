# Purchase

Fire whenever a user purchases one or more items.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "purchase",
  affiliation: "<affiliation>",
  coupon: "<coupon>",
  currency: "<currency>",
  items: "<items>",
  shipping: "<shipping>",
  tax: "<tax>",
  transaction_id: "<transaction_id>",
  value: "<value>"
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|affiliation|string|recommended|A product affiliation to designate a supplying company or brick and mortar store location. Event-level and item-level affiliation parameters are independent.|`walgreens`|`^[A-Za-z0-9_]+$`|
|coupon|string|recommended|The coupon name/code associated with the event. Event-level and item-level coupon parameters are independent.|`SUMMER_FUN`|`^[A-Za-z0-9_]+$`|
|currency|string|required|Currency of the items associated with the event, in 3-letter ISO 4217 format.|`USD`|`^[A-Z]{3}$`|3|3|
|items|array of [items](/schemas/item.md)|required|Populate with [item](/schemas/item.md) objects that represent the product(s) purchased.|`[{item_id: "test"}]`
|shipping|number|recommended|Shipping cost associated with a transaction.|`3.33`|`^\d\.\d\d$`|||0.00|
|tax|number|recommended|Tax cost associated with a transaction.|`1.11`|`^\d\.\d\d$`|||0.00|
|transaction_id|string|required|The unique identifier of a transaction.|`T12345`|
|value|number|required|The monetary value of the event.|`7.77`|`^\d\.\d\d$`|||0.00|