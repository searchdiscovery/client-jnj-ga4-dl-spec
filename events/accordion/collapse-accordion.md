# Collapse Accordion

Fire whenever a user collapses an accordion item.

If using data attributes, the `data-layer-event` attribute should be dynamically updated from `expand_accordion` to `collapse_accordion` whenever the accordion is expanded so this event will fire.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="collapse_accordion",
  data-layer-identifier="<identifier>"
  data-layer-name="<name>"
  data-layer-heading="<heading>"
  data-layer-index="<index>"
  data-layer-type="<type>"
>
```
## Javascript Code

```js
// When:
// User collapses accordion item.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "collapse_accordion",
  event_data: {
    identifier: "<identifier>", // REQUIRED | string | ID of the accordion (ie "tab-menu-2814--2")
    name: "<name>", // optional | string | name of the accordion (ie "beauty-products")
    heading: "<heading>", // REQUIRED | string | text heading of the accordion (ie "Beauty")
    index: "<index>", // optional | string | slot number of the accordion item (ie "4") | 1-indexed
    type: "<type>" // optional | string | accordion type (ie "product")
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|required|The computer-readable machine name of the accordion. Use UUID provided by the component.|12345abcde12345|
|name|string|recommended|The human-readable name of the accordion. If user does not input one, populate with numerical index of which accordion this is on the page (1-indexed). FAQs are the big one that currently need to be broken out in reporting, so getting a name for those should be the priority.|FAQs, 2|
|heading|string|required|The text heading of the accordion item that was opened/closed|"Are our products safe?"|
|index|integer|recommended|The ordinal slot number of the accordion item. E.g. - the top item in the accordion will be slot 1. (1-indexed)|1||1||1|
|type|integer|recommended|The type of accordion.|FAQ, product|