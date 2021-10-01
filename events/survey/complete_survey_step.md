# Complete Survey Step

Fire whenever a user successfully completes a survey step/section. 

This event is fired when a step/section of a survey is successfully received and process. This is in contrast to [`survey_error`](survey/survey_error.md) which occurs when a submission is attempted but an error occurs and the survey input is not recieved and processed.

It is importand to note that step_choices that include PII (e.g. freeform input fields, first name, last name, email address, home address, etc.) should be **_EXCLUDED_** from this data layer event. For more information, please visit [Understanding PII in Google's contracts and policies](https://support.google.com/analytics/answer/7686480?hl=en).

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'survey_complete',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
  step_choice: '<step_choice>',  // Only radio buttons or select lists
  step_name: '<step_name>,
  step_number: 1
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The survey machine-readible name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `event_specific_name`.|cancel_subscription_flow, free_trial|
|event_specific_name|string|required|The survey human-readible name. This should be something that an analyst without a deep knowledge of the technical implementatino of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
|step_choice|string|recommended|The human-readable, user-selected value(s) within a step/section of a survery.|Too Expensive,Using Another Product/Brand|
|step_name|string|recommended|The human-readable name of the current step of the survey.|why_are_you_cancelling,which_product|
|step_number|integer|recommended|The current step/section integer of the survey flow.|1,2,3,4,5|
