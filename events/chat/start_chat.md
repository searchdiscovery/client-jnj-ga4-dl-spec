# Start Chat

Fire whenever a user initiates a chat session. 

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'start_chat',
  event_data: {
    event_specific_id: '<event_specific_id>',
    event_specific_name: '<event_specific_name>',
    event_specific_type: '<event_specific_type>'
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|event_specific_id|string|optional|The chat machine-readable name. This should be a unique value specific to this chat prompt, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|ecp_locator, free_trial|
|event_specific_name|string|optional|The chat prompt human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the chat with. It should be lowercase snake_case.|ecp_locator, free_trial|
|event_specific_type|string|optional|The chat type. This will act as a filtering mechanism in reporting to enable analysts to view chat droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating chats require a `generate_lead` event to be fired alongside `chat_complete`, and that could be written into the logic based upon this field.|contact, lead_generation|