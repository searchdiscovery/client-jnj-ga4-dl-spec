# Start Review

Fire whenever a user modifies the first field on a review widget. 

An [item](/schemas/item) object should be included, but not as a separate property or array. The keys and values of the item should be rolled into the base object being pushed...hence the spread operator syntax used in the JS code below.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'start_review',
  event_data: {
    ...item
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|...item|[item](/schemas/item.md)|recommended|Properties representing the product being reviewed.|{item_id: "test"}
