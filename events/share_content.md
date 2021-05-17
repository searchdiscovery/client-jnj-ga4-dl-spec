# Share Content

Fire whenever a user shares content via email or social. 

The parameters page_title and page_location are automatically sent along on each page view and should be able to contextualize this event without any additional information being needed.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="share_content"
  data-layer-method="<method>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'share_content',
  method: '<method>'
});
```

## Variable Definitions

|Field|Type|Required?|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|method|string|The platform used to share content|email, facebook, twitter|