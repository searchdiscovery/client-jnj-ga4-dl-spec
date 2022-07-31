# Select Indication

Fire whenever a user selects a drug indication or specialty.

## Javascript Code

```js
// When:
// User user selects a drug indicatino or specialy

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'select_indication',
  event_data: {
    indication: '<indication>', //recommended | string | ex. dermatology, rheumatology	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|indication|string|recommended|The indication or specialty selected by the user|dermatology, rheumatology|
