# Filter Item Category

Fire whenever a user clicks on a Product Category filter.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous ecommerce object.
dataLayer.push({
  event: "filter_item_category",
  event_data: {
    event_specific_id: "<event_specific_id>",
    event_specific_name: "<event_specific_name>",
    event_specific_type: "<event_specific_type>"
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The filter machine-readable name. This should be a unique value specific to this filter, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|hand_lotions, beauty_creams|
|event_specific_name|string|required|The filter human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the filter with. It should be lowercase snake_case.|"Hand Lotions", "Beauty Creams"|
|event_specific_type|string|required|The filter type. This will act as a filtering mechanism in reporting to enable analysts to view filter engagement.||