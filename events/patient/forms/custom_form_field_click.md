# Form Field Click

Fire when a user engages with a field in a form. This is to help capture when users are engaging with components and can be helped to understand drop-off based on features.

## Javascript Code

```js
// When:
// Fire when a user engages with a field in a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_view',
  event_data: {
    form_name: <form_name>, 
    step_name: <step_name>, 
    step_number: <step_number>, 
    field_name: <field_name>, 
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
|step_name|string|required|The name of the step users are interacting with|Support Personalization|
|step_number|integer|required|Step number in a predefined form flow. Should correspond to step number shown to users on page|1,2,3|
|field_name|string|required|The name of the form field|firstName,lastName,phoneNumber|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|
|person|string|required|Persona of user, e.g. patient or caregiver|patient, caregiver|
|prescription_status|string|required|Currently prescribed or not currently prescribed|currently prescribed darzalex|
|condition|string|required|Medical condition that the patient is seeking help with|Moderate to Severe Plaque Psoriasis|
|pathway|string|required|Pathway used. e.g. Full Program, Cost Support Only, Guide Only.|dedicatedGuide. costSupport|
