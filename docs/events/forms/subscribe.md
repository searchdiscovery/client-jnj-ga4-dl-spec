# Subscribe

Fire whenever a user subscribes to an email or product.

## HTML Data Attributes

TBD

## Javascript Code

```js
// When:
// User subscribes to an email or product

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'subscribe',
  event_data: {
    identifier: '<identifier>', // recommended | string | ex. neutrogena_newsletter_123, jnj_promos_123
    name: '<name>', // REQUIRED | string | ex. neutrogena_newsletter, jnj_promos
    type: '<type>', // REQUIRED | string | ex. newsletter, promos
    method: '<method>' // recommended | string | ex. email
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|recommended|The subscription machine-readable name. This should be a unique value specific to this subscription, if one exists. If one does not exist, this can also be populated with the same value as the `name`.|neutrogena_newsletter_123, jnj_promos_123|
|name|string|required|The subscription human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the subscription with. It should be lowercase snake_case.|neutrogena_newsletter, jnj_promos|
|type|string|required|The subscription type. This will act as a filtering mechanism in reporting to enable analysts to view subscription droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating subscriptions require a `generate_lead` event to be fired alongside `form_complete`, and that could be written into the logic based upon this field.|newsletter, promos|
|method|string|recommended|The channel through which the subscription is delivered. This is usually email, but can also be product.|email|