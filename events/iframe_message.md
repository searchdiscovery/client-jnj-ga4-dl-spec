# iFrame message

Fire whenever an iframe emits a message using the `window.postMessage` method.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'iframe_message',
  iframe_category: "<iframe_category>",
  iframe_category2: "<iframe_category2>",
  iframe_classes: "<iframe_classes>",
  iframe_domain: "<iframe_domain>",
  iframe_element: "<iframe_element>",
  iframe_id: "<iframe_id>",
  iframe_payload: "<iframe_payload>",
  iframe_url: "<iframe_url>",
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|iframe_category|string|recommended|The general category of the iFrame.|Where to Buy Widget, Audio|
|iframe_category2|string|recommended|The subcategory of the iFrame.|Shoppable, Podcast|
|iframe_classes|string|contextual|The iFrame CSS classes.|audio-embed|
|iframe_domain|string|required|The hostname of the iFrame source.|`vimeo.com`| 
|iframe_element|[HTMLIFrameElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)|required|The iFrame HTML element.|`<iframe src="neutrogena.com/iframe" ...>`|
|iframe_id|string|contextual|The iFrame HTML ID attribute.|hero-video|
|iframe_url|string|required|The full URL of the iFrame source.|`where-to-buy.co`|