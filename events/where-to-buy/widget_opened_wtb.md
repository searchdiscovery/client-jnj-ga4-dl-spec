# Widget Opened WTB

Fire whenever a user successfully opens a WTB widget.

## Javascript Code

```js
// When:
// User successfully opens the WTB tool.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "widget_opened_wtb",
  event_data: {
    component_type: "<component_type>", // REQUIRED | string | ex. PriceSpider, ChannelAdvisor
    item_brand: "<item_brand>", // REQUIRED | string | ex. Tylenol, Zyrtec, Listerine
    item_id: "<item_id>", // REQUIRED | string | ex. CW21001
    item_name: "<item_name>", // REQUIRED | string | ex.
    item_upc: "<item_upc>" // contextual | string | ex. 012345678905 (12 digits)
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_type|string|required|The human-readable name of the WTb tool |PriceSpider, ChannelAdvisor|
|item_brand|string|required|The human-readable brand name. |Tylenol, Zyrtec, Listerine|
|item_id|string|required|SKU id of product||
|item_name|string|required|The human-readable product name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case.||
|item_upc|string|contextual|UPC ID of the product a customer would be calling a store about.|`012345678905`|
