# Single Accordion

Fire whenever a user interacts with an accordion.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'expand_accordion' || 'collapse_accordion',
  accordion_id: "<accordion_id>",
  accordion_name: "<accordion_id>",
  accordion_heading: "<accordion_heading>",
});
```

## Variable Definitions

|Field|Type|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|accordion_id|string|The computer-readible machine name of the carousel. Use UUID provided by the component|12345abcde12345|required|
|accordion_name|string|The human-readible name of the carousel. If user does not input one, populate with numerical index of which carousel this is on the page (1-indexed)|Most Popular Blog Posts, 2|preferred|
|heading|string|The heading of the accordion item opened/closed||