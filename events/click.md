# Click

These events will be automatically detected and fired for any `<a>` tag clicked by a user. The data attributes and events are primarily here for cases in which a non anchor tag is used as a link. 

For example, if a `<button>` tag is used in combination with Javascript to represent a download link, you would need to add these attributes to manually fire the event.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="click"
  data-layer-component_ancestry="<component_ancestry>"
  data-layer-event_specific_category="<event_specific_category>"
  data-layer-event_specific_category2="<event_specific_category2>"
  data-layer-event_specific_category3="<event_specific_category3>"
  data-layer-event_specific_category4="<event_specific_category4>"
  data-layer-event_specific_category5="<event_specific_category5>"
  data-layer-event_specific_id="<event_specific_id>"
  data-layer-event_specific_name="<event_specific_name>"
  data-layer-event_specific_type="<event_specific_type>"
  data-layer-link_classes="<link_classes>"
  data-layer-link_id="<link_id>"
  data-layer-link_text="<link_text>"
  data-layer-link_url="<link_url>"
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
  event: "click",
  event_data: {
    component_ancestry: "<component_ancestry>",
    event_specific_category: "<event_specific_category>",
    event_specific_category2: "<event_specific_category2>",
    event_specific_category3: "<event_specific_category3>",
    event_specific_category4: "<event_specific_category4>",
    event_specific_category5: "<event_specific_category5>",
    event_specific_id: "<event_specific_id>",
    event_specific_name: "<event_specific_name>",
    event_specific_type: "<event_specific_type>",
    link_classes: "<link_classes>",
    link_id: "<link_id>",
    link_text: "<link_text>",
    link_url: "<link_url>",
    navigation_ancestry: "<navigation_ancestry>",
    outbound: "<outbound>",
    region_ancestry: "<region_ancestry>",
  }
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|component_ancestry|string|recommended|A delimited string showing all components in the ancestry of the link clicked|hero~product carousel
|event_specific_category|string|optional|Optional field that enables you to assign this link a specific category. Used primarily when you want to analyze the performance of a group of links that aren't connected by component_ancestry, region_ancestry, link_url, or link_text.|cta_links, wtb_links|
|event_specific_category[2-5]|string|optional|Optional fields that enable you to assign this link additional subcategories beyond event_specific_category.|cta_links, wtb_links|
|event_specific_id|string|optional|Optional field that enables you to assign this link a specific ID. Used primarily when you need to identify a link and component_ancestry, region_ancestry, link_classes, link_id, link_text, and link_url are not sufficient to do that.||
|event_specific_type|string|required|Records the type of link that was clicked. The type here refers to what comes before the :// on the link itself. Useful for identifying http links that should be https, as well as reporting on mailto, tel, and other alternate link types|http, https, tel, mailto|
|link_classes|string|required|The list of HTML/CSS classes applied to the link.|button-red|
|link_domain|string|required|The domain of the link.|example.com|
|link_id|string|required|The HTML/CSS ID of the link.|submit-button|
|link_text|string|required|The full text of the link.|click here|
|link_url|string|required|The full URL of the link.|https://www.example.com/form|
|navigation_ancestry|string|recommended|A delimited string showing all navigation items in the ancestry of link clicked in a multi-tiered menu|about~our leadership~our CEO|
|outbound|boolean|conditional|Does the link point to a different domain?|false|
|region_ancestry|string|recommended|A delimited string showing all regions in the ancestry of the link clicked|header~navigation