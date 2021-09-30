# View Form

Fire whenever a user is presented with a form on a page.

## HTML Data Attributes

This could be done with data attributes and detected via GTM at DOM Ready, but if a form is dynamically added to the page at any time, it would not be picked up. As such, manually firing the data layer push whenever a form is loaded is a more reliable approach.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'view_form',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
  event_specific_type: '<event_specific_type>'
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The form machine-readible name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|event_specific_name|string|required|The form human-readible name. This should be something that an analyst without a deep knowledge of the technical implementatino of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|event_specific_type|string|required|The form type. This will act as a filtering mechanism in reporting to enable analysts to view form droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating forms require a `generate_lead` event to be fired alongside `form_complete`, and that could be written into the logic based upon this field.|contact, lead_generation|