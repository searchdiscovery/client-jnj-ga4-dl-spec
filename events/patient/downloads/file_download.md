# File Download

These events will be automatically detected and fired for any link clicked by the user that leads to a file. The data attributes and events are primarily here for cases in which a non anchor tag is used as a link. 

For example, if a `<button>` tag is used in combination with Javascript to represent a download link, you would need to add these attributes to manually fire the event.


## Javascript Code

```js

// Code
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "file_download",
  event_data: {
    file_extension: "<file_extension>", // recommended | string | ex. pdf
    link_url: "<link_url>", // REQUIRED | string | ex. https://www.example.com/form
    link_text: "<link_text>", // REQUIRED | string | ex. download pdf
    
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|file_extension|string|recommended|The file extension of the file being downloaded.|pdf|
|link_text|string|required|The full text of the link.|click here|
|link_url|string|required|The full URL of the link.|https://www.example.com/form|

