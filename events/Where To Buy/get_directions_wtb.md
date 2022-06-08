# Get Directions WTB

Fire whenever a user successfully opens a WTB widget.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'get_directions_wtb',
  event_data: {
    compontent_type: '<compontent_type>',
    item_name: '<item_name>'
    item_sku: '<item_sku>',
    item_upc: '<item_sku>',
    item_brand: '<item_brand>',
    link_url: '<item_brand>',
    affiliation: '<item_brand>',
  },
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|compontent_type|string|required|The human-readable name of the WTB Provider. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case.|PriceSpider, ChannelAdvisor|
|item_name|string|required|The human-readable product name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case||
|item_sku|string|required|SKU id of product||
|item_brand|string|required|The human-readable name of the brand. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|Tylenol, Zyretc, Lsiterine|
|link_url|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|www.amazon.com|
|affiliation|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|Wallmart, CVS|
