# Form Step Complete

Fire when a user completes a form. This is to help capture when users are engaging with components and can be helped to understand drop-off based on features.

## Javascript Code

```js
// When:
// Fire when a user engages with a field in a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_step_complete',
  event_data: {
    form_name: <form_name>, 
    step_name: <step_name>, 
    insurance_coverage: <insurance_coverage>, 
    insurance_assistance: <insurance_assistance>,
    has_savings_card: <has_savings_card>, 
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
|insurance_coverage|string|required|The type of insurance coverage for the patient|
|insurance_assistance|string|required|Insurance assistance selection for the patient|
|has_savings_card|string|required|Indicates whether patient already has a savings card|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|
|person|string|required|Persona of user, e.g. patient or caregiver|patient, caregiver|
|prescription_status|string|required|Currently prescribed or not currently prescribed|currently prescribed darzalex|
|condition|string|required|Medical condition that the patient is seeking help with|Moderate to Severe Plaque Psoriasis|
|pathway|string|required|Pathway used. e.g. Full Program, Cost Support Only, Guide Only.|dedicatedGuide. costSupport|
