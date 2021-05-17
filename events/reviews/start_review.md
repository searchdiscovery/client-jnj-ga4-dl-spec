# Start Review

Fire whenever a user modifies the first field on a review widget.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'start_review',
  item_id: <item_id>,
  item_name: <item_name>,
  item_brand: <item_brand>,
  item_category: <item_category>,
  item_category2: <item_category2>,
  item_category3: <item_category3>,
  item_category4: <item_category4>,
  item_variant: <item_variant>
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|item_id|string|required|The ID of the product.|SDI1234|
|item_name|string|recommended|The human-readible name of the product.|15 Oz Widgets|
|item_brand|string|recommended|The product's brand.|Neutrogena, Aveeno|
|item_category|string|recommended|The product's category.||
|item_category2|string|optional|The product's subcategory.||
|item_category3|string|optional|The product's tier-3 category.||
|item_category4|string|optional|The product's tier-4 category.||
|item_variant|string|recommended|The variant of the product.||