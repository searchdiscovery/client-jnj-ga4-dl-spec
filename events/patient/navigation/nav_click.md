# Nav Click

Send when a user clicks on navigation elements (such as Top Nav or Footer)

## Javascript Code
```js
// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'nav_click',
  event_data: {   
    link_url: <link_url>, 
    link_text: <link_text>,
    element_name: <element_name>,
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
|element_name|string|required|Name of site element a user interacted with.|
|link_url|string|required|The HREF of the link interacted with.|
|link_text|string|required|The text of the link interacted with.|
|brand|string|required|Prescription drug that patients are familiar with|darzalex, erleada|
|person|string|required|Persona of user, e.g. patient or caregiver|patient, caregiver|
|prescription_status|string|required|Currently prescribed or not currently prescribed|currently prescribed darzalex|
|condition|string|required|Medical condition that the patient is seeking help with|Moderate to Severe Plaque Psoriasis|
|pathway|string|required|Pathway used. e.g. Full Program, Cost Support Only, Guide Only.|dedicatedGuide. costSupport|

