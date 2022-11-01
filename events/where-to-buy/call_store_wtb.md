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
  event: "call_store_wtb",
  event_data: {
    affiliation: "<affiliation>", // REQUIRED | string | ex. walmart, cvs
    component_type: "<component_type>", // REQUIRED | string | ex. pricespider, channeladvisor
    item_brand: "<item_brand>", // REQUIRED | string | ex. tylenol, zyrtec, listerine
    item_id: "<item_id>", // REQUIRED | string | ex. CW21001
    item_name: "<item_name>", // REQUIRED | string | ex. essential_foaming_cleanser 
    item_upc: "<item_upc>", // **Unknown** | string | ex. 012345678905 (12 digits)
    link_url: "<link_url>" // REQUIRED | string | ex. https://www.example.com/?q=product#id
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|affiliation|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|`walmart`, `cvs`|
|component_type|string|required|The human-readable name of the WTB Provider. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case.|`pricespider`, `channeladvisor`|
|item_brand|string|required|The human-readable name of the brand. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|`tylenol`, `zyrtec`, `listerine`|
|item_id|string|required|SKU ID of the product a customer would be calling a store about.|`CW21001`|
|item_name|string|required|The human-readable product name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|`essential_foaming_cleanser`|
|item_upc|string|contextual|UPC ID of the product a customer would be calling a store about.|`012345678905`|
|link_url|string|required|This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify. It should be lowercase snake_case|`https://www.example.com?q=product#id`|
