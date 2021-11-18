# Select Tab

Fire whenever a user selects a tab item.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="select_tab"
  data-layer-event_specific_id="<event_specific_id>"
  data-layer-event_specific_name="<event_specific_name>"
  data-layer-event_specific_heading="<event_specific_heading>"
  data-layer-slot="<slot>"
>
```
## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "select_tab",
  event_data: {
    event_specific_id: "<event_specific_id>",
    event_specific_name: "<event_specific_name>",
    event_specific_heading: "<event_specific_heading>",
    slot: "<slot>",
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|required|The computer-readable machine name of the tab. Use UUID provided by the component|12345abcde12345|
|event_specific_name|string|recommended|The human-readable name of the tab. If user does not input one, populate with numerical index of which tab this is on the page (1-indexed). FAQs are the big one that currently need to be broken out in reporting, so getting a name for those should be the priority.|FAQs, 2|
|event_specific_heading|string|required|The text heading of the tab item that was opened/closed|"Are our products safe?"|
|slot|integer|recommended|The ordinal slot number of the tab item. E.g. - the top item in the tab will be slot 1. (1-indexed)|1||1||1|
