# Previous Carousel Slide

Fire whenever a user interacts with the previous carousel slide control

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="previous_carousel_slide"
  data-layer-identifier="<identifier>"
  data-layer-name="<name>"
  data-layer-index="<index>"
  data-layer-target_index="<target_index>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'previous_carousel_slide',
  event_data: {
    identifier: "<identifier>",
    name: "<name>",
    index: "<index>",
    target_index: "<target_index>"
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|required|The computer-readable machine name of the carousel. Use UUID provided by the component|12345abcde12345|
|name|string|recommended|The human-readable name of the carousel. If user does not input one, populate with numerical index of which carousel this is on the page (1-indexed)|Most Popular Blog Posts, 2|
|index|integer|recommended|The slide # the carousel is on at time of interaction (1-indexed)|1||1||1
|target_index|integer|recommended|The slide # of the target slide (1-indexed)|2||1||1|
