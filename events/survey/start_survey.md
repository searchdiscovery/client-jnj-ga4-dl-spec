# Start Survey

Fire whenever a user starts filling out a survey. 

This event is generally fired after user input in the first survey field. Historically this has been done via an HTMLElement change event on a survey field, though it could be done via an HTMLElement focus event on a survey field instead if that proves easier to implement. It should only be fired once per survey, but if that is too technically complicated to implement, it can be limited on the GTM side instead.

## HTML Data Attributes

This could be done with data attributes and detected via GTM at DOM Ready, but if a survey is dynamically added to the page at any time, it would not have the listeners properly set up. As such, manually firing the data layer push whenever a survey is submitted is a more reliable approach.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'start_survey',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The survey machine-readable name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|cancel_subscription_flow, free_trial|
|event_specific_name|string|required|The survey human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
|event_specific_type|string|required|The survey type. This will act as a filtering mechanism in reporting to enable analysts to view survey droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating surveys require a `generate_lead` event to be fired alongside `complete_survey`, and that could be written into the logic based upon this field.|survey, lead_generation|
