# Login

Fire whenever a user logs in to an account.

## Javascript Code

```js
// When:
// User logs into an account

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "login",
  event_data: {
    method: "<method>", // recommended | string | ex. google, linkedin, email and password
  },
  page_data: {
    user_login_state: '<user_login_state>', // optional | string | ex. authenticated, anonymous
  },
  user_data: {
    user_id: "<user_id>", // recommended | string | ex. 1234567890
    user_type: '<user_type>' // optional | string | ex. new, returning
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|method|string|recommended|The method used to login.|google, linkedin, email and password|
|user_id|string|recommended|The user identifier|1234567890|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|
|user_type|string|contextual|Set on all events with the authentication type of the visitor are they new or returning|new, returning|
