# Error Type

Fire whenever a user unsuccessfully completes a form. 

This is in contrast to `form_complete` which occurs when a submission succeeds.

## Javascript Code

```js
// When:
// User unsuccessfully completes a form and data is not received or processed

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_error',
  event_data: {
    error_message: '<error_message>', // REQUIRED | string | ex. Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address
    error_type: '<error_type>' // recommended | string | ex. form_field_validation, server_error	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|error_message|string|required|The specific error that occurred. If an error message is shown to the user, this should be populated with that text.|Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address|
|error_type|string|recommended|Differentiates between a frontend or backend error|form_field_validation, server_error|

