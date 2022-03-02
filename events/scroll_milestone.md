# Scroll Milestone

Fire when a user scrolls past a certain scroll depth. The built-in `scroll` event can be set up to automatically on 90% scroll depth, but this event will allow for more milestones to be recorded.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'scroll_milestone',
  event_data: {
    milestone: '<milestone>'
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|milestone|string|required|The depth to which user scrolled on the page.|25,50,75|
