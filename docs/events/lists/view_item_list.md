# View Item (Product) List

Fire whenever a user sees multiple product links in a list that forward the user to the product detail page. 

This event should also be fired for the "Filter By Group" component when the list is initially displayed or updated after a facet is applied...but only when that component contains products.

## Javascript Code

```js
// When:
// User sees multiple product links in a list that forward to a product detail page
// 'Filter By Group' component list is initially displayed or updated after a facet is applied, but only for products

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "view_item_list",
  ecommerce: {
    facets: "<facets>", // optional | string - double delimited (:)(~) | ex. category:skin_health~featured_as:best_seller	
    items: "<items>", // REQUIRED | array | ex. [{item_id: "070501110485", item_name: "Neutrogena Hydro Boost Gel-Cream"}]	
    item_list_id: "<item_list_id>", // recommended | string | ex. 12345abcde12345
    item_list_name: "<item_list_name>", // recommended | string | ex. filter_by_group, recommended_products, recently_viewed_products
    list_type: "<list_type>", // optional | string | ex. cards, search_results	
    search_term: "<search_term>", // optional | string | ex. sunscreen
    search_type: "<search_type>", // optional | string | ex. site, filter_by_group
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|facets|delimited string|contextual|A double-delimited string of key/value pairs representing the refinements that were applied if this list is displayed using the "Filter By Group" component.|category:skin_health\~skin_concern:acne\~featured_as:best_seller|
|items|array of [items](/schemas/item.md)|recommended|Populate with item objects that represent each product in the list.|[{item_id: "test"}]
|item_list_id|string|recommended|The computer-readable machine name of the list the item showed up in. Use UUID provided by the component if no more specific ID is available.|12345abcde12345|
|item_list_name|string|recommended|The human-readable name of the list the item showed up in. If one is not available, populate with numerical index of which list this is on the page (1-indexed). For `filter_by_group` component, use that value.|filter_by_group, recommended_products, recently_viewed_products, search_results|
|list_type|string|contextual|The type of list the item was found in.|cards, search_results|
|search_term|string|contextual|The final search term submitted after any correction has been performed. Only set if the `list_type` is `search_results`.|sunscreen|
|search_type|string|contextual|The type of search performed. Only set if the `list_type` is `search_results`.|site, filter_by_group|