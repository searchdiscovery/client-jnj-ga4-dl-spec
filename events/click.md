# Click

These events will be automatically detected and fired for any `<a>` tag clicked by a user. The data attributes and events are primarily here for cases in which a non anchor tag is used as a link. 

For example, if a `<button>` tag is used in combination with Javascript to represent a download link, you would need to add these attributes to manually fire the event.

## HTML Data Attributes

```html
<button
  data-layer-event="click"
  data-layer-category="<category>"
  data-layer-category2="<category2>"
  data-layer-category3="<category3>"
  data-layer-category4="<category4>"
  data-layer-category5="<category5>"
  data-layer-identifier="<identifier>"
  data-layer-link_text="<link_text>"
  data-layer-link_url="<link_url>"
  data-layer-outbound="<outbound>"
  data-layer-type="<type>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "click",
  event_data: {
    component_ancestry: "<component_ancestry>",
    category: "<category>",
    category2: "<category2>",
    category3: "<category3>",
    category4: "<category4>",
    category5: "<category5>",
    identifier: "<identifier>",
    link_classes: "<link_classes>",
    link_id: "<link_id>",
    link_text: "<link_text>",
    link_url: "<link_url>",
    navigation_ancestry: "<navigation_ancestry>",
    outbound: "<outbound>",
    region_ancestry: "<region_ancestry>",
    type: "<type>",
  }
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_ancestry|string|recommended|A delimited string showing all components in the ancestry of the link clicked|hero~product carousel
|category|string|optional|Optional field that enables you to assign this link a specific category. Used primarily when you want to analyze the performance of a group of links that aren't connected by component_ancestry, region_ancestry, link_url, or link_text.|cta_links, wtb_links|
|category[2-5]|string|optional|Optional fields that enable you to assign this link additional subcategories beyond category.|cta_links, wtb_links|
|identifier|string|optional|Optional field that enables you to assign this link a specific ID. Used primarily when you need to identify a link and component_ancestry, region_ancestry, link_classes, link_id, link_text, and link_url are not sufficient to do that.||
|link_classes|string|required|The list of HTML/CSS classes applied to the link.|button-red|
|link_domain|string|required|The domain of the link.|example.com|
|link_id|string|required|The HTML/CSS ID of the link.|submit-button|
|link_text|string|required|The full text of the link.|click here|
|link_url|string|required|The full URL of the link.|https://www.example.com/form|
|navigation_ancestry|string|recommended|A delimited string showing all navigation items in the ancestry of link clicked in a multi-tiered menu|about~our leadership~our CEO|
|outbound|boolean|conditional|Does the link point to a different domain?|false|
|region_ancestry|string|recommended|A delimited string showing all regions in the ancestry of the link clicked|header~navigation|
|type|string|required|Records the type of link that was clicked. The type here refers to what comes before the :// on the link itself. Useful for identifying http links that should be https, as well as reporting on mailto, tel, and other alternate link types|http, https, tel, mailto|
