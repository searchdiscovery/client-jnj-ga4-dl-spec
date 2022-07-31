# Form View

Fire whenever a user is presented with a form on a page.

## HTML Data Attributes

This could be done with data attributes and detected via GTM at DOM Ready, but if a form is dynamically added to the page at any time, it would not be picked up. As such, manually firing the data layer push whenever a form is loaded is a more reliable approach.

## Javascript Code

```js
// When:
// User presented a form on a page

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_view',
  event_data: {
    identifier: '<identifier>', // recommended | string | ex. ecp_locator, free_trial
    name: '<name>', // REQUIRED | string | ex. ecp_locator, free_trial	
    type: '<type>' // REQUIRED | string | ex. contact, lead_generation
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|type|string|required|The form type. This will act as a filtering mechanism in reporting to enable analysts to view form droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating forms require a `generate_lead` event to be fired alongside `form_complete`, and that could be written into the logic based upon this field.|contact, lead_generation|