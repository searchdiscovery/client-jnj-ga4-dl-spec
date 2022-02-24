# Logout

Fire whenever a user logs out of an account.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "logout",
  user_data: {
    user_id: "<user_id>",
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|user_id|string|recommended|The user identifier|1234567890|