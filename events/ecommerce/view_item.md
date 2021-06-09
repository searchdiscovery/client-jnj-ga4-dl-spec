# View Item

Fire whenever a user visits a product detail page.

This event will eventually fully replace the "Product Viewed" event currently being sent on product detail pages. For now, we'd like to have both implemented so the changeover is simple when it's time to do so. Given that, this is a relatively low priority event to implement.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "view_item",
  currency: "<currency>",
  items: "<items>",
  value: "<value>"
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|currency|string|recommended|Currency of the items associated with the event, in 3-letter ISO 4217 format.|USD|
|items|array of [items](/schemas/item.md)|required|Populate with item objects that represent the product viewed.|[{item_id: "test"}]
|value|number|recommended|The monetary value of the event.|7.77|