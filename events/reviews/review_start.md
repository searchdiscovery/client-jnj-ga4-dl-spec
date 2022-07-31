# Review Start

Fire whenever a user modifies the first field on a review widget. 

An [item](/schemas/item) object should be included, but not as a separate property or array. The keys and values of the item should be rolled into the base object being pushed...hence the spread operator syntax used in the JS code below.

## Javascript Code

```js
// When:
// User modifies the first field on a review widget

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'review_start',
  event_data: {
    item_id: "<item_id>" //Required | string | ex. 12345
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|item_id|string|required|The ID of the product being reviewed.|12345|
