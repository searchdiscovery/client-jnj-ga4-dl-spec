# Survey Error

Fire whenever a user unsuccessfully completes a survey. 

This is in contrast to [`complete_survey`](survey/complete_survey.md) which occurs when a submission succeeds.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'survey_error',
  error: '<error>',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|error|string|required|The specific error that occurred. If an error message is shown to the user, this should be populated with that text.|Phone number should follow the surveyat (xxx) xxx-xxxx, Must be a valid email address|
|event_specific_id|string|recommended|The survey machine-readable name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `event_sepcific_name`.|cancel_subscription_flow, free_trial|
|event_specific_name|string|required|The survey human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
|event_specific_type|string|recommended|The type of error that occurred.|survey_field_validation, server_error|
