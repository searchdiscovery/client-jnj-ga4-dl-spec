# Scroll

Fire when a user scrolls past a certain scroll depth. The built-in event fires automatically on 90% scroll depth, but customizing will allow for more control of triggering logic for user scroll engagement.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: '<scroll>',
  event_data: {
    percent_scrolled: '<percent_scrolled>'
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|percent_scrolled|string|required|The depth to which user scrolled on the page.|10,25,50,75|
