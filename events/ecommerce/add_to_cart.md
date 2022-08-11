# Add To Cart

Fire whenever a user adds one or more items to their cart.

## Javascript Code

```js
// When:
// User adds one or more items to cart

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "add_to_cart",
  ecommerce: {
    currency: "<currency>", // recommended | string | ex. USD | pattern: ^[A-Z]{3}$ | min. 3, max. 3
    items: "<items>", // REQUIRED | array | ex. [{item_id: "test"}]
    value: "<value>" // recommended | number | ex. 7.77 | pattern: ^\d\.\d\d$	 | min. 0.00
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|currency|string|recommended|Currency of the items associated with the event, in 3-letter ISO 4217 format.|USD|^[A-Z]{3}$|3|3|
|items|array of [items](/schemas/item.md)|required|Populate with item objects that represent the product viewed.|[{item_id: "test"}]
|value|number|recommended|The monetary value of the event.|7.77|^\d\.\d\d$|||0.00|