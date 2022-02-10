# Expand Accordion

Fire whenever a user expands an accordion item.

If using data attributes, the `data-layer-event` attribute should be dynamically updated from `collapse_accordion` to `expand_accordion` whenever the accordion is collapsed so this event will fire.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="expand_accordion",
  data-layer-accordion_id="<accordion_id>"
  data-layer-accordion_name="<accordion_name>"
  data-layer-index="<index>"
>
```
## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "expand_accordion",
  event_data: {
    accordion_id: "<accordion_id>",
    accordion_name: "<accordion_name>",
    accordion_heading: "<accordion_heading>",
    index: "<index>",
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|accordion_id|string|required|The computer-readable machine name of the accordion. Use UUID provided by the component|12345abcde12345|
|accordion_name|string|recommended|The human-readable name of the accordion. If user does not input one, populate with numerical index of which accordion this is on the page (1-indexed). FAQs are the big one that currently need to be broken out in reporting, so getting a name for those should be the priority.|FAQs, 2|
|heading|string|required|The text heading of the accordion item that was opened/closed|"Are our products safe?"|
|index|integer|recommended|The ordinal slot number of the accordion item. E.g. - the top item in the accordion will be slot 1. (1-indexed)|1||1||1|