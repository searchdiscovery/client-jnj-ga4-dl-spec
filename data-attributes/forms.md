# Forms

Add the following attributes to every form HTML element.

## HTML Data Attributes

```html
<form
  data-layer-event_specific_id="<event_specific_id>"
  data-layer-event_specific_name="<event_specific_name>"
>
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|recommended|The form machine-readible name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|event_specific_name|string|required|The form human-readible name. This should be something that an analyst without a deep knowledge of the technical implementatino of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
