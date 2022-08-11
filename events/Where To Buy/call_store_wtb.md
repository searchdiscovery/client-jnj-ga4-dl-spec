# Call Store WTB

Fire whenever a user successfully calls a store.

## Javascript Code

```js
// When:
// User successfully calls a store.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'call_store_wtb',
  event_data: {
    component_type: '<component_type>', // REQUIRED | string | ex. PriceSpider, ChannelAdvisor
    item_name: '<item_name>', // REQUIRED | string | ex. 
    item_sku: '<item_sku>', // REQUIRED | string | ex. CW21001
    item_upc: '<item_upc>', // **Unknown** | string | ex. 012345678905 (12 digits)
    item_brand: '<item_brand>', // REQUIRED | string | ex. Tylenol, Zyrtec, Listerine
    link_url: '<item_brand>', // REQUIRED | string | ex. www.amazon.com
    affiliation: '<item_brand>', // REQUIRED | string | ex. Walmart, CVS
  },
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_type|string|required|The human-readable name of the WTB Provider. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case.|PriceSpider, ChannelAdvisor|
|item_name|string|required|The human-readable product name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case||
|item_sku|string|required|SKU id of product||
|item_brand|string|required|The human-readable name of the brand. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|Tylenol, Zyrtec, Listerine|
|link_url|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|www.amazon.com|
|affiliation|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|Walmart, CVS|
