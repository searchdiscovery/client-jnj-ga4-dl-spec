# Location Set WTB

Fire whenever a user successfully sets their location. 

## Javascript Code

```js
// When:
// User successfully sets their location.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "location_set_wtb"
});
```

## Variable Definitions

This event has no parameters.
