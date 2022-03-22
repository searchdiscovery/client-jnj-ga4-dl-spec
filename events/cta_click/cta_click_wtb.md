# CTA Click WTB

This event will be automatically detected and fired if the data attributes below are added to each link

## HTML Data Attributes

```html
<div
  data-layer-event="cta_click_wtb"
  data-layer-affiliation="<affiliation>"
  data-layer-category="<category>"
  data-layer-link_text="<link_text>"
  data-layer-link_url="<link_url>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "cta_click_wtb",
  event_data: {
    category: "<category>",
    link_text: "<link_text>",
    link_url: "<link_url>",
    type: "<type>",
  }
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|affiliation|string|recommended|A product affiliation that designates the product retailer.|Amazon.com,Walmart.com,CVS|
|category|string|optional|Used to differentiate |find online,find locally|
|link_text|string|required|The full text of the link if the link text represents an action (e.g. - Add to Cart, Buy Now, Get Directions, etc.). If the text of the link represents just information, send a description of the information. (e.g. - for store hours of 8:00-16:00 send "store hours") |Add to Cart, Buy Now, Get Directions, store hours|
|link_url|string|required|The full URL of the link.|https://www.example.com/form|