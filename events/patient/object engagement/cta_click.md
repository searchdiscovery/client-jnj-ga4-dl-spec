# Cta Click

When a user clicks a CTA, defined as oval buttons with a specific call-to-action, except for CONTINUE buttons to complete a step.

## Javascript Code
```js
// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'cta_click',
  event_data: {
    step_name: <step_name>,
    step_number: <step_number>,
    link_url: <link_url>, 
    link_text: <link_text>,
    module_name: <module_name>, 
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
|step_name|string|required|The name of the step users are interacting with|Support Personalization|
|step_number|integer|required|Step number in a predefined form flow. Should correspond to step number shown to users on page|1,2,3|
|link_url|string|required|The HREF of the link interacted with.|
|link_text|string|required|The text of the link interacted with.|
|module_name|string|required|Name of content module on the site|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|
|person|string|required|Persona of user, e.g. patient or caregiver|patient, caregiver|
|prescription_status|string|required|Currently prescribed or not currently prescribed|currently prescribed darzalex|
|condition|string|required|Medical condition that the patient is seeking help with|Moderate to Severe Plaque Psoriasis|
|pathway|string|required|Pathway used. e.g. Full Program, Cost Support Only, Guide Only.|dedicatedGuide. costSupport|

