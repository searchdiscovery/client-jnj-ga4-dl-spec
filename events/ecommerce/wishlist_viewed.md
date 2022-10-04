# View Wishlist

Send when a user views their wishlist.

## Javascript Code

```js
// When:
// User user views their wishlist

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ ecommerce: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "wishlist_viewed",
  ecommerce: {
    items: "<items>", // REQUIRED | array | ex. [{item_id: "test"}]
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|items|array of [items](/schemas/item.md)|required|Populate with item objects that represent the items viewed.|`[{item_id: "test"}]`
