# Survey Step Complete

Fire whenever a user successfully completes a survey step/section. 

This event is fired when a step/section of a survey is successfully received and process. This is in contrast to [`survey_error`](survey/survey_error.md) which occurs when a submission is attempted but an error occurs and the survey input is not recieved and processed.

It is important to note that the `step_choice` attrbiute which can possibly include PII (e.g. freeform input fields, first name, last name, email address, home address, etc.) should be **_EXCLUDED_** from this data layer event. For more information, please visit [Understanding PII in Google's contracts and policies](https://support.google.com/analytics/answer/7686480?hl=en).

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'survey_step_complete',
  event_data: {
    identifier: '<identifier>',
    name: '<name>',
    type: '<type>',
    step_choice: '<step_choice>',  // Only radio buttons or select lists
    step_choice_method: '<step_choice_method>',
    step_name: '<step_name>',
    step_number: 1
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The survey machine-readable name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|cancel_subscription_flow, free_trial|
|name|string|required|The survey human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
|type|string|required|The survey type. This will act as a filtering mechanism in reporting to enable analysts to view survey droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating surveys require a `generate_lead` event to be fired alongside `complete_survey`, and that could be written into the logic based upon this field.|survey, lead_generation|
|step_choice|string|recommended|The human-readable, user-selected value(s) within a step/section of a survey.|Too Expensive,Using Another Product/Brand|
|step_choice_method|string|recommended|This was initially scoped for skin360 as the survey can assign you a primary skin concern or you can choose one yourself. It can be used beyond that application for any time you need additional context around the step choice.|automatic,user-selected|
|step_name|string|recommended|The human-readable name of the current step of the survey.|why_are_you_cancelling,which_product|
|step_number|integer|recommended|The current step/section integer of the survey flow.|1,2,3,4,5|
