# Click

These events will be automatically detected and fired for any `<a>` tag clicked by a user. The data attributes and events are primarily here for cases in which a non anchor tag is used as a link. For example, if a `<button>` tag is used in combination with Javascript to represent a download link, you would need to add these attributes to manually fire the event.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="click"
  data-layer-link_classes="<link_classes>"
  data-layer-link_domain="<link_domain>"
  data-layer-link_id="<link_id>"
  data-layer-link_cta_type="<link_cta_type>"
  data-layer-link_url="<link_url>"
  data-layer-download="<download>"
  data-layer-hash="<hash>"
  data-layer-javascript="<javascript>"
  data-layer-mailto="<mailto>"
  data-layer-outbound="<outbound>"
  data-layer-telephone="<telephone>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: "click",
  link_classes: "<link_classes>",
  link_domain: "<link_domain>",
  link_id: "<link_id>",
  link_url: "<link_url>",
  hash: "<hash>",
  javascript: "<javascript>",
  mailto: "<mailto>",
  outbound: "<outbound>",
  telephone: "<telephone>",
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|link_classes|string|The list of HTML/CSS classes applied to the link.|button-red|
|link_domain|string|The domain of the link.|example.com|
|link_id|string|The HTML/CSS ID of the link.|submit-button|
|link_cta_type|string|The type of CTA the link click represents.|view_product, generate_lead|
|link_url|string|The full URL of the link.|https://www.example.com/form|
|hash|boolean|Does the link point to a different domain?|false|
|javascript|boolean|Does the link point to a fragment within the page (jump link)?|false|
|mailto|boolean|Does the link point to an email address?|false|
|outbound|boolean|Does the link point to a different domain?|false|
|telephone|boolean|Does the link point to a telephone number?|false|