# Change Item SKU

Fire whenever a user successfully changes the sku they are looking at within the WTB tool.

## Javascript Code

```js
// When:
// User successfully changes the sku they are looking at within the WTB tool.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'change_item_sku_wtb',
  event_data: {
    component_type: '<component_type>', // REQUIRED | string | ex. PriceSpider, ChannelAdvisor
    item_name: '<item_name>', // REQUIRED | string | ex. 
    item_sku: '<item_sku>', // REQUIRED | string | ex. CW21001
    item_upc: '<item_upc>', // **Unknown** | string | ex. 012345678905 (12 digits)
    item_brand: '<item_brand>', // REQUIRED | string | ex. Tylenol, Zyrtec, Listerine
  },
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_type|string|recommended|The human-readable name of the WTB Provider. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case.|PriceSpider, ChannelAdvisor|
|item_name|string|required|The form human-readable product name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.||
|item_sku|string|required|SKU id of product||
|item_brand|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|Tylenol, Zyrtec, Listerine|
