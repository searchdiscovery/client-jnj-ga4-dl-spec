# Select Indication

Fire whenever a user selects a drug indication or specialty.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'select_indication',
  indication: '<indication>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|indication|string|recommended|The indication or specialty selected by the user|dermatology, rheumatology|
