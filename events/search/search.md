# Search

Fire whenever a user performs a search of any kind. This includes product searches, content searches, resource searches, etc. and does not require a view_search_results event to be fired subsequent to it.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "search",
  corrected_term: "<corrected_term>"
  search_term: "<search_term>",
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|corrected_term|string|recommended|The initial search term before typeahead/lookahead/suggestion, if the site has those features.|suns|
|search_term|string|required|The final search term submitted after any correction has been performed|sunscreen|

## Notes
Discussed potentially adding search_type but all searches are global full-text searches so there isn't a search type concept at time of initial search.