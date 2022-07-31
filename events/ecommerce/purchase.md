# Purchase

Fire whenever a user purchases one or more items.

## Javascript Code

```js
// When:
// User purchases on or more items

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "purchase",
  ecommerce: {
    affiliation: "<affiliation>", //recommended | string | ex. walgreens | pattern: ^[A-Za-z0-9_]+$	
    coupon: "<coupon>", //recommended | string | ex. SUMMER_FUN | pattern: ^[A-Za-z0-9_]+$ 
    currency: "<currency>", //Required | string | ex. USD | pattern: ^[A-Z]{3}$ | min. 3, max. 3
    items: "<items>", //Required | array | ex. [{item_id: "test"}]
    shipping: "<shipping>", //recommended | number | ex. 3.33 | pattern: ^\d\.\d\d$	| min. 0.00
    tax: "<tax>", //recommended | number | ex. 1.11 | pattern: ^\d\.\d\d$	| min. 0.00
    transaction_id: "<transaction_id>", //Required | string | T12345
    value: "<value>" //Required | number | ex. 7.77 | pattern: ^\d\.\d\d$	| min. 0.00
  }
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