# Form Complete

Fire whenever a user successfully completes a form. 

This event is fired when form input is successfully received and process. This is in contrast to `form_error` which occurs when a submission is attempted but an error occurs and the form input is not recieved and processed.

## Javascript Code

```js
// When:
// Fire when a user engages with a field in a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_complete',
  event_data: {
    form_name: <form_name>, 
    eligibility_outcome: <eligibility_outcome>,
    support_program_options: <support_program_options>,
    brand: <brand>, 
    person: <person>, 
    prescription_status: <prescription_status>, 
    condition: <condition>, 
    pathway: <pathway>
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|form_name|string|required|Used with the "form_complete", or "form_error" events, this parameter returns the form name.|Digital Enrollment Form|
|support_program_options|string|required|Support Program Options enrolled by user|
|eligibility_outcome|string|required|If user is eligible or not for program |Not eligible|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|
|person|string|required|Persona of user, e.g. patient or caregiver|patient, caregiver|
|prescription_status|string|required|Currently prescribed or not currently prescribed|currently prescribed darzalex|
|condition|string|required|Medical condition that the patient is seeking help with|Moderate to Severe Plaque Psoriasis|
|pathway|string|required|Pathway used. e.g. Full Program, Cost Support Only, Guide Only.|dedicatedGuide. costSupport|
