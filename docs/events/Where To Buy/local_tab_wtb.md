# Switch to Local Tab

Fire whenever a user successfully switches to the local tab within the WTB tool.

## Javascript Code

```js
// When:
// User successfully switches to the local tab within the WTB tool.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'local_tab_wtb',
  event_data: {
    category: '<category>', // recommended | string | ex. (unique form value, if one exists)
  },
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|category|string|recommended|This should be a unique value specific to this form, if one exists. ||
