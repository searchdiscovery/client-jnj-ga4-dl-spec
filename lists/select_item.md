# Select Item

Fire whenever a user clicks on a product link found in a list that forwards the user to the product detail page. List types include cards, search, promotions, and similar component.

If the list type is not currently able to support differentiating products from content, then add the attributes/event for **[select_content](select content)** instead and add a dev task to update the list type to enable this differentiation.

Do not fire this event for product links found in menus.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="select_item"
  data-layer-facets="<facets>"
  data-layer-list_type="<list_type>"
  data-layer-search_term="<search_term>"
  data-layer-search_term="<search_type>"
  data-layer-slot="<slot>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "select_item",
  facets: "<facets>",
  list_type: "<list_type>",
  search_term: "<search_term>",
  search_type: "<search_type>",
  slot: "<slot>",
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|contextual|A double-delimited string of key/value pairs representing the refinements that were applied to this search. Only set if the list type is a search result or filter_by_group.|category:skin_health~skin_concern:acne~featured_as:best_seller|
|list_type|string|contextual|The type of list the item was found in.|cards, search_results|
|item_list_id|string|recommended|The computer-readible machine name of the list the item showed up in. Use UUID provided by the component if no more specific ID is available.|12345abcde12345|
|item_list_name|string|recommended|The human-readible name of the list the item showed up in. If one is not available, populate with numerical index of which list this is on the page (1-indexed). For `filter_by_group` component, use that value.|filter_by_group, recommended_products, recently_viewed_products|
|search_term|string|contextual|The final search term submitted after any correction has been performed. Only set if the `list_type` is `search_results`.|sunscreen|
|search_type|string|contextual|The type of search performed. Only set if the `list_type` is `search_results`.|site, filter_by_group|
|slot|integer|required|The numerical index of the item position (1-indexed). For instance, if this is the 5th search result, you would send 5 here. If this is the 3rd card in a single row, send 3. If this is the 2nd item in the 3rd row of a 3-up card layout, send 8 (3 + 3 + 2).|5|