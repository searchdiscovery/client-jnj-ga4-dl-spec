# Submit Form

Fire whenever a user submits a form. 

This event is fired after user submits a form. Historically this has been done via an HTMLElement submit event on the form itself and can be picked up automatically through GTM as long as the data attributes have been added. However, if the form is submitted asynchronously through JS this event may never actually fire as a JS handler runs instead. In that case, the data layer event will need to be manually pushed.

## HTML Data Attributes

This could be done with data attributes and detected via GTM at DOM Ready, but if a form is dynamically added to the page at any time, it would not have the listeners properly set up. As such, manually firing the data layer push whenever a form is submitted is a more reliable approach.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'submit_form',
  event_specific_id: '<event_specific_id>',
  event_specific_name: '<event_specific_name>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The form machine-readible name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|event_specific_name|string|required|The form human-readible name. This should be something that an analyst without a deep knowledge of the technical implementatino of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
