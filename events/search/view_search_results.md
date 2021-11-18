# View Search Results

Fire whenever a user views search results. This includes product searches, content searches, resource searches, etc. and does not require a search event to be fired prior to it.

This event should also be considered for the "Filter By Group" component if it is ever used to display anything but products. When used in this way, the search_term parameter would be `filter_by_group` as that component does not currently allow for a search_term to be entered by the user. If this case does arise, contact Search Discovery for additional information.
## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "view_search_results",
  event_data: {
    facets: "<refinements>",
    result_count: "<result_count>",
    search_term: "<search_term>",
    search_type: "<search_type>",
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|recommended|A delimited string of key/value pairs representing the facets that were applied to this search|need:skin health\~skin_concern:acne\~featured_as:best_seller|
|result_count|integer|recommended|The total number of search results found|324|
|search_term|string|required|The final search term submitted after any correction has been performed|sunscreen|
|search_type|string|required|The type of search performed|ecp_locator,filter_by_group,product,site|

## Notes

A lot of thought was put into whether to keep this as its own event as it's not in the Google event spec currently and `view_item_list` could potentially cover it. However, `view_item_list` is really only meant for products and doesn't inherently indicate that a search took place. For this reason, this seems the best way to split up the events. This event indicates a search result list was displayed but provides no information about what was in that list. `view_item_list` indicates a list of products was displayed and captures each individual item. If overlap is ever needed for reporting, this could be reworked.
