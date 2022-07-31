# Detect User

This is a conditional event that should only be fired in very specific cases. It is intended to cover cases where a user authentication system exists on the site but the user authentication state may not be known by the time the page_view event is sent. In that case, send this event as soon as the user authentication state is known.

Do not clear the page_data variable before setting user_login_state here as this is not a page view.

## Javascript Code

```js
// When:
// User authentication exists, but the 'authentication state' may not be known by the time the page_view event is fired.
// NOTE: Do not clear the page_data variable before setting user_login_state here. This is not a page view.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "detect_user",
  page_data: {
    user_login_state: '<user_login_state>', //recommended | string | ex. 1234567890	
  },
  user_data: {
    user_id: "<user_id>", //optional | string | ex. authenticated, anonymous
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|user_id|string|recommended|The user identifier|1234567890|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|