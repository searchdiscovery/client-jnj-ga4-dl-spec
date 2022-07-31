# Form Complete

Fire whenever a user successfully completes a form. 

This event is fired when form input is successfully received and process. This is in contrast to `form_error` which occurs when a submission is attempted but an error occurs and the form input is not recieved and processed.

## Javascript Code

```js
// When:
// User successfully completes a form and data is received and processed

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_complete',
  event_data: {
    identifier: '<identifier>', //recommended | string | ex. ecp_locator, free_trial	
    name: '<name>', //Required | string | ex. ecp_locator, free_trial	
    type: '<type>' //Required | string | ex. contact, lead_generation	
  },
  user_data: {
    user_id: '<user_id>', //optional | string | ex. 12345
    user_login_state: '<user_login_state>', //optional | string | ex. authenticated, anonymous	
    event_form_custkey: '<SFMC_CustomerKey>', //Required | string | ex. 12345...
    event_form_hashemail: '<HashedEmail>' //Required | string | ex. b642b4217b34b1e8d3bd915fc65c4452 (MD5)
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|type|string|required|The form type. This will act as a filtering mechanism in reporting to enable analysts to view form droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating forms require a `generate_lead` event to be fired alongside `form_complete`, and that could be written into the logic based upon this field.|contact, lead_generation|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|  
|event_form_custkey|string|required|This is the ID created by Salesforce Marketing cloud||
|event_form_hashemail|string|required|Converts the submitted email into hased format|
