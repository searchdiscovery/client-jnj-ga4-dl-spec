# View Search Results

Fire whenever a user views search results. This includes product searches, content searches, resource searches, etc. and does not require a search event to be fired prior to it.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "view_search_results",
  facets: "<refinements>",
  result_count: "<result_count>",
  search_term: "<search_term>",
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|A delimited string of key/value pairs representing the facets that were applied to this search|need:skin health~skin_concern:acne~featured_as:best_seller|
|result_count|integer|The total number of search results found|324|
|search_term|string|The final search term submitted after any correction has been performed|sunscreen|