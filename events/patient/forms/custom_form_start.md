# Form Start

Fire whenever a user starts filling out a form. 

This event is generally fired after user input in the first form field. Historically this has been done via an HTMLElement change event on a form field, though it could be done via an HTMLElement focus event on a form field instead if that proves easier to implement. It should only be fired once per form, but if that is too technically complicated to implement, it can be limited on the GTM side instead.



## Javascript Code

```js
// When:
// User starts to fill our a form. Event fires after user input into the first form field 
// and should only fire once. onchange(), onfocus(), and GTM may be helpful.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_start',
  event_data: {
    identifier: '<identifier>', // recommended | string | ex. ecp_locator, free_trial	
    form_name: <form_name>, // REQUIRED | string | ex. ecp_locator, free_trial	
    step_name: <step_name>, // REQUIRED | string | ex. contact, lead_generation
    step_number: <step_number>,
    brand: <brand>,
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|form_name|string|required|Used with the "form_complete", or "form_error" events, this parameter returns the form name.|Digital Enrollment Form|
|step_name|string|required|The name of the step users are interacting with|Support Personalization|
|step_number|integer|required|Step number in a predefined form flow. Should correspond to step number shown to users on page|1,2,3|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|

