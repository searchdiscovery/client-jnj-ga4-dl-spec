# Select Search Result

Fire whenever a user clicks on a search result or add these data layer attributes to each search result link.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="select_search_result"
  data-layer-facets="<facets>"
  data-layer-search_term="<search_term>"
  data-layer-slot="<slot>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "select_search_result",
  facets: "<facets>",
  search_term: "<search_term>",
  slot: "<slot>",
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|recommended|A double-delimited string of key/value pairs representing the refinements that were applied to this search|category:skin_health~skin_concern:acne~featured_as:best_seller|
|search_term|string|required|The final search term submitted after any correction has been performed|sunscreen|
|slot|integer|required|The numerical index of the search result position (1-indexed)|5|