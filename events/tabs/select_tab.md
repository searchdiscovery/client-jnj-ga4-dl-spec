# Select Tab

Fire whenever a user selects a an item out of a tabset that asynchronously updates the page. Do not use this for navigation menus as those should be covered by [menu data attributes](/data-attributes/menus.md).

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="select_tab"
  data-layer-identifier="<identifier>"
  data-layer-name="<name>"
  data-layer-heading="<heading>"
  data-layer-index="<index>"
>
```
## Javascript Code

```js
// When:
// User selects an item in a tabset that asynchronously updates page. Not for navigation menu use.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "select_tab",
  event_data: {
    identifier: "<identifier>", // REQUIRED | string | ex. 12345abcde12345
    name: "<name>", // recommended | string | ex. FAQs, 2
    heading: "<heading>", // REQUIRED | string | ex. Are our products safe?
    index: "<index>", // recommended | integer | ex 1, 5
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|required|The computer-readable machine name of the tab. Use UUID provided by the component|12345abcde12345|
|name|string|recommended|The human-readable name of the tab. If user does not input one, populate with numerical index of which tab this is on the page (1-indexed). FAQs are the big one that currently need to be broken out in reporting, so getting a name for those should be the priority.|FAQs, 2|
|heading|string|required|The text heading of the tab item that was opened/closed|"Are our products safe?"|
|index|integer|recommended|The ordinal slot number of the tab item. E.g. - the top item in the tab will be slot 1. (1-indexed)|1||1||1|
