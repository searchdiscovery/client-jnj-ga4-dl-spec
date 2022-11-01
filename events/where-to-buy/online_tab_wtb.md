# Switch to Online Tab

Fire whenever a user successfully switches to the online tab wiithin the WTB tool.

## Javascript Code

```js
// When:
// User successfully switches to the online tab within the WTB tool.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "online_tab_wtb",
  event_data: {
    category: "<category>"
  },
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|category|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the `<name>`.|pricespider, channeladvisor|
