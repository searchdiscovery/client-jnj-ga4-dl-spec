# Form Error

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
    error_message: '<error_message>', //Required | string | ex. Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address
    identifier: '<identifier>', //recommended | string | ex. ecp_locator, free_trial	
    name: '<name>', //Required | string | ex. ecp_locator, free_trial
    type: '<type>' //recommended | string | ex. form_field_validation, server_error	
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|error_message|string|required|The specific error that occurred. If an error message is shown to the user, this should be populated with that text.|Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address|
|identifier|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|type|string|recommended|The type of error that occurred.|form_field_validation, server_error|
