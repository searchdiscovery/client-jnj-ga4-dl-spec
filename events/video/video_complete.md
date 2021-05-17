# Video Progress

Fire whenever a video ends. This will usually be picked up automatically by GTM on desktop but may need to be manually sent on mobile.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'video_complete',
  video_current_time: '{{video_current_time}}',
  video_duration: '{{video_duration}}',
  video_percent: '{{video_percent}}',
  video_provider: '{{video_provider}}',
  video_title: '{{video_title}}',
  video_url: '{{video_url}}',
  visible: '{{visible}}',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|video_current_time|string|required|The current time of the video viewed.|15|
|video_duration|string|required|The total duration of the video.|600|
|video_percent|string|required|The current percent of the video viewed.|15|
|video_provider|string|required|The video provider.|youtube, vimeo|
|video_title|string|required|The title of the video.|Walkthrough of the Google Analytics 4 User Interface|
|video_url|string|required|The URL of the video.|https://youtu.be/RhS85WQiBLU|
|visible|boolean|required|Is the video visible on the page.|true|