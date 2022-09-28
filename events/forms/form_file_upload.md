# Form Complete

Fire whenever a user successfully uploads a file (such as a receipt) within a form.


## Javascript Code

```js
// When:
// User successfully uploads a file (like a receipt) within a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'form_file_upload',
  event_data: {
    identifier: '<identifier>', // recommended | string | ex. ecp_locator, free_trial	
    name: '<name>', // REQUIRED | string | ex. ecp_locator, free_trial	
    type: '<type>', // REQUIRED | string | ex. contact, lead_generation
    file_extension: '<file_extension>', // recommended | string | ex. pdf
    file_name: '<file_name>' // recommended | string | ex. example.pdf
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The form machine-readable name. This should be a unique value specific to this form, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|name|string|required|The form human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the form with. It should be lowercase snake_case.|ecp_locator, free_trial|
|type|string|required|The form type. This will act as a filtering mechanism in reporting to enable analysts to view form droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating forms require a `generate_lead` event to be fired alongside `form_complete`, and that could be written into the logic based upon this field.|contact, lead_generation|
|file_extension|string|recommended|The file extension of the file being uploaded.|pdf|
|file_name|string|recommended|The filename of the file being uploaded.|drug_facts.pdf|
