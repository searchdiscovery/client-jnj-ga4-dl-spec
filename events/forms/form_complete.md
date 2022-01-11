# Form Complete

Fire whenever a user successfully completes a form. 

This event is fired when form input is successfully received and process. This is in contrast to `form_error` which occurs when a submission is attempted but an error occurs and the form input is not recieved and processed.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_complete',
  event_data: {
    event_specific_id: '<event_specific_id>',
    event_specific_name: '<event_specific_name>',
    event_specific_type: '<event_specific_type>'
  },
  user_data: {
    user_id: '<user_id>',
    user_login_state: '<user_login_state>',
    event_form_custkey: '<event_specific_SFMC_CustomerKey>',
    event_form_hashemail: '<event_specific_HashedEmail>'
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|event_specific_name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|  
|event_form_custkey|string|required|This is the ID created by Salesforce Marketing cloud||
|event_form_hashemail|string|required|Converts the submitted email into hased format|
