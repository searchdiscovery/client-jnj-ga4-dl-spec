# Page View

Fire whenever a user loads in a new page, whether that is done synchronously or asynchronously.

This event should be the first pushed into the data layer on each page. Given many 3rd party scripts push events to the data layer, this event push should be placed in the page `<head>` and should be the first `<script>` tag on the page to ensure it is the first event.

There is no longer a concept of virtual page view, so this event should be fired whenever a virtual page view would have been fired in the past, such as when a new screen is loaded asyncronously within an angular, react, or vue app/embed.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: '<page_view>',
  brand: '<brand>',
  country: '<country>',
  language: '<language>',
  page_category: '<page_category>',
  page_location: '<page_location>',
  page_referrer: '<page_referrer>', 
  page_title: '<page_title>',
  page_name: '<page_name>',
  region: '<region>',
  site_section: '<site_section>',
  user_id: '<user_id>',
  user_login_state: '<user_login_state>',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|brand|string|required|The brand the site is associated with.|neutrogena|
|country|string|required|The country the site is associated with.|us|
|language|string|required|The language of the current page, usually pulled from the `<html>` tag `lang` attribute.|en|
|page_category|string|required|Used for grouping pages (or screens) into high level categories.|article,blog,homepage,product|
|page_location|string|required|The url of the page currently being viewed.|https://www.neutrogena.com|
|page_referrer|string|required|The previous page URL, generally available in `document.referrer`|https://www.neutrogena.com|
|page_title|string|required|The title of the page currently being viewed, generally available in `<title>`.|https://www.neutrogena.com|
|page_title|string|required|The low-level, client-defined name of the page currently being viewed.|homepage,search results,product:neutrogena hydro boost gel|
|region|string|required|The region the site is associated with.|EMEA|
|site_section|string|recommended|The section of the site that the current page resides in. `site_section2` through `site_section5`can also be used if the site has many sections.|products|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|

## Notes
- This is the first version with baseline parameters. There will be many additional parameters coming over time as more and more sites are added with differing requirements.
