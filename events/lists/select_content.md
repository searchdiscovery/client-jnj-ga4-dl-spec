# Select Content

Fire whenever a user clicks on a content link found in a list that forwards the user to the content page. List types include cards, search, promotions, and similar component. 

Do not fire this event for content links found in menus.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="select_content"
  data-layer-facets="<facets>"
  data-layer-identifier="<identifier>"
  data-layer-index="<index>"
  data-layer-list_type="<list_type>"
  data-layer-name="<name>"
  data-layer-search_term="<search_term>"
  data-layer-search_term="<search_type>"
>
```

## Javascript Code

```js
// When:
// User user clicks clicks on a content link found in a list (cards, search, promotions...) that forwards to the content page

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "select_content",
  event_data: {
    content_type: "<content_type>", //recommended | string | ex. article, blog, page	
    facets: "<facets>", //optional | string - double delimited (:)(~) | category:skin_health~featured_as:best_seller	
    identifier: "<identifier>", //recommended | string | ex. ecp_locator, free_trial
    index: "<index>", //Required | integer | ex. 5
    list_type: "<list_type>", //optional | string | ex. cards, search_results	
    name: "<name>", //Required | string | ex. purchase_product
    search_term: "<search_term>", //optional | string | ex. sunscreen
    search_type: "<search_type>", //optional | string | site, filter_by_group	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|content_type|string|recommended|The type of content selected by the user. Use "page" if no more specific content_type applies or if the capability to distinguish between content_types does not currenly exist.|article, blog, page|

|facets|delimited string|contextual|A double-delimited string of key/value pairs representing the refinements that were applied to this search. Only set if the list type is a search result or filter_by_group.|category:skin_health~skin_concern:acne~featured_as:best_seller|
|identifier|string|recommended|The form machine-readable name. This should be a unique value specific to this piece of content, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|index|integer|required|The numerical index of the item position (1-indexed). For instance, if this is the 5th search result, you would send 5 here. If this is the 3rd card in a single row, send 3. If this is the 2nd item in the 3rd row of a 3-up card layout, send 8 (3 + 3 + 2).|5|
|list_type|string|contextual|The type of list the item was found in.|cards, search_results|
|name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.||
|search_term|string|contextual|The final search term submitted after any correction has been performed. Only set if the `list_type` is `search_results`.|sunscreen|
|search_type|string|contextual|The type of search performed. Only set if the `list_type` is `search_results`.|site, filter_by_group|
