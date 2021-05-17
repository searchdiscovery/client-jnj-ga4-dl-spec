# Expand Accordion

Fire whenever a user expands an accordion item.

## HTML Data Attributes

```html
<a href=""
  data-layer-event="expand_accordion",
  data-layer-accordion_id="<accordion_id>"
  data-layer-accordion_name="<accordion_name>"
  data-layer-slot="<slot>"
>
```
## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "expand_accordion",
  accordion_id: "<accordion_id>",
  accordion_name: "<accordion_name>",
  accordion_heading: "<accordion_heading>",
  slot: "<slot>",
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|accordion_id|string|required|The computer-readible machine name of the accordion. Use UUID provided by the component|12345abcde12345|
|accordion_name|string|recommended|The human-readible name of the accordion. If user does not input one, populate with numerical index of which carousel this is on the page (1-indexed)|FAQs, 2|
|heading|string|required|The text heading of the accordion item that was opened/closed|"Are our products safe?"|
|slot|integer|recommended|The ordinal slot number of the accordion item. E.g. - the top item in the accordion will be slot 1. (1-indexed)|1||1||1|