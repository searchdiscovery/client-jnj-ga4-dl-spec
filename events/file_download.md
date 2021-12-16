# File Download

These events will be automatically detected and fired for any link clicked by the user that leads to a file. The data attributes and events are primarily here for cases in which a non anchor tag is used as a link. 

For example, if a `<button>` tag is used in combination with Javascript to represent a download link, you would need to add these attributes to manually fire the event.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="click"
  data-layer-component_ancestry="<component_ancestry>"
  data-layer-file_extension="<file_extension>"
  data-layer-file_name="<file_name>"
  data-layer-link_cta_id="<link_cta_id>"
  data-layer-link_url="<link_url>"
  data-layer-link_id="<link_id>"
  data-layer-link_classes="<link_classes>"
  data-layer-link_text="<link_text>"
  data-layer-link_href_type="<link_href_type>"
  data-layer-navigation_ancestry="<navigation_ancestry>"
  data-layer-outbound="<outbound>"
  data-layer-region_ancestry="<region_ancestry>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "file_download",
  event_data: {
    component_ancestry: "<component_ancestry>",
    file_extension: "<file_extension>",
    file_name: "<file_name>",
    link_cta_id: "<link_cta_id>",
    link_url: "<link_url>",
    link_id: "<link_id>",
    link_classes: "<link_classes>",
    link_text: "<link_text>",
    link_href_type: "<link_href_type>",
    navigation_ancestry: "<navigation_ancestry>",
    outbound: "<outbound>",
    region_ancestry: "<region_ancestry>",
  }
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_ancestry|string|recommended|A delimited string showing all components in the ancestry of the link clicked|hero~product carousel|
|file_extension|string|recommended|The file extension of the file being downloaded.|pdf|
|file_name|string|recommended|The filename of the file being downloaded.|drug_facts.pdf|
|link_cta_id|string|optional|Optional field that enables you to categorize this link beyond its containing components, regions, text, and href. Use a delimited categorization heirarchy.|For instance, "careers~apply" and "careers~view opportunity".|
|link_classes|string|required|The list of HTML/CSS classes applied to the link.|button-red|
|link_domain|string|required|The domain of the link.|example.com|
|link_href_type|string|recommended|
|link_id|string|required|The HTML/CSS ID of the link.|submit-button|
|link_url|string|required|The full URL of the link.|https://www.example.com/form|
|navigation_ancestry|string|recommended|A delimited string showing all navigation items in the ancestry of link clicked in a multi-tiered menu|about~our leadership~our CEO|
|outbound|boolean|conditional|Does the link point to a different domain?|false|
|region_ancestry|string|recommended|A delimited string showing all regions in the ancestry of the link clicked|header~navigation