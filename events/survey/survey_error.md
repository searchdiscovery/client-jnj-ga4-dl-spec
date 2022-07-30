# Survey Error

Fire whenever a user unsuccessfully completes a survey. 

This is in contrast to [`complete_survey`](survey/complete_survey.md) which occurs when a submission succeeds.

## Javascript Code

```js
// When:
// User unsuccessfully completes a survey and survey input is not sucessfully received and processed. Contrasts survey_complete in which a submission is recieved and processed sucessfully. 

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'survey_error',
  event_data: {
    error_message: '<error_message>', //Required | string | ex. Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address
    identifier: '<identifier>', //recommended | string | ex. cancel_subscription_flow, free_trial
    name: '<name>', //Required | string | ex. cancel_subscription_flow, free_trial
    type: '<type>', //Required | string | ex. survey, lead_generation
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|error_message|string|required|The specific error that occurred. If an error message is shown to the user, this should be populated with that text.|Phone number should follow the format (xxx) xxx-xxxx, Must be a valid email address|
|identifier|string|recommended|The survey machine-readable name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|cancel_subscription_flow, free_trial|
|name|string|required|The survey human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
|type|string|recommended|The type of error that occurred.|survey_field_validation, server_error|
|step_name|string|recommended|The human-readable name of the current step of the survey.|why_are_you_cancelling,which_product|
|step_number|integer|recommended|The current step/section integer of the survey flow.|1,2,3,4,5|
