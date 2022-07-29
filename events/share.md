# Share

Fire whenever a user shares content via email or social. 

The parameters page_title and page_location are automatically sent along on each page view and should be able to contextualize this event without any additional information being needed.

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="share"
  data-layer-content_type="<content_type>"
  data-layer-item_id="<item_id>"
  data-layer-method="<method>"
>
```

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'share',
  event_data: {
    content_type: '<content_type>', // required | string | type of content | ex. blog, landing, content, product
    item_id: '<item_id>', // recommended | string | product primary ID | ex. SKU CW21001 or UPC 012345678905
    method: '<method>' // required | string | social platform | ex. email, facebook, twitter
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|content_type|string|required|The type of content shared|blog, content, home, landing, product|
|item_id|string|recommended|The product primary ID (SKU or UPC) if it is a product being shared|123456|
|method|string|required|The platform used to share content|email, facebook, twitter|