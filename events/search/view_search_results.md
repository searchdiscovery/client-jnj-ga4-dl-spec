# View Search Results

Fire whenever a user views search results. This includes product searches, content searches, resource searches, etc. and does not require a search event to be fired prior to it. 

This event should also be fired for the "Filter By Group" component whenever the list is initially displayed or updated after a facet is applied. When used in this way, the search_term parameter should always be `filter_by_group` as that component does not currently allow for a search_term to be entered by the user.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "view_search_results",
  facets: "<refinements>",
  result_count: "<result_count>",
  search_term: "<search_term>",
  search_type: "<search_type>",
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|A delimited string of key/value pairs representing the facets that were applied to this search|need:skin health~skin_concern:acne~featured_as:best_seller|
|result_count|integer|The total number of search results found|324|
|search_term|string|The final search term submitted after any correction has been performed|sunscreen|
|search_type|string|required|The type of search performed|product,site|
