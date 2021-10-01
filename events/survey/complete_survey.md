# Survey Complete

Fire whenever a user successfully completes a survey. 

This event is fired when survey input is successfully received and process. This is in contrast to [`survey_error`](survey/survey_error.md) which occurs when a submission is attempted but an error occurs and the survey input is not recieved and processed.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'survey_complete',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The survey machine-readible name. This should be a unique value specific to this survey, if one exists. If one does not exist, this can also be populated with the same value as the `event_specific_name`.|cancel_subscription_flow, free_trial|
|event_specific_name|string|required|The survey human-readible name. This should be something that an analyst without a deep knowledge of the technical implementatino of the site can easily identify the survey with. It should be lowercase snake_case.|cancel_subscription_flow, free_trial|
