# Review Complete

Fire whenever a user completes a review. 

An [item](/schemas/item) object should be included, but not as a separate property or array. The keys and values of the item should be rolled into the base object being pushed...hence the spread operator syntax used in the JS code below.

## Javascript Code

```js
// When:
// User completes a review

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'review_complete',
  event_data: {
    rating: "<rating>", //Required | string | ex. 12345
    item_id: "<item_id>" //recommended | string | ex. 3
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|item_id|string|required|The ID of the product being reviewed.|12345|
|rating|string|recommended|The numerical rating given to the product.|3|
