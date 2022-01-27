# Page View

Fire whenever a user loads in a new page, whether that is done synchronously or asynchronously.

This event should be the first pushed into the data layer on each page. Given many 3rd party scripts push events to the data layer, this event push should be placed in the page `<head>` and should be the first `<script>` tag on the page to ensure it is the first event.

There is no longer a concept of virtual page view, so this event should be fired whenever a virtual page view would have been fired in the past, such as when a new screen is loaded asyncronously within an angular, react, or vue app/embed.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({ page_data: null, user_data: null });  // Clear the previous attributes.
dataLayer.push({
  event: 'page_view',
  page_data: {
    brand: '<brand>',
    country: '<country>',
    event_specific_category: '<event_specific_category>',
    event_specific_category2: '<event_specific_category2>',
    event_specific_category3: '<event_specific_category3>',
    event_specific_category4: '<event_specific_category4>',
    event_specific_category5: '<event_specific_category5>',
    event_specific_id: '<event_specific_id>',
    event_specific_type: '<event_specific_type>',
    language: '<language>',
    page_location: '<page_location>',
    page_referrer: '<page_referrer>', 
    page_title: '<page_title>',
    region: '<region>',
    site_section: '<site_section>',
    site_section2: '<site_section2>',
    site_section3: '<site_section3>',
    site_section4: '<site_section4>',
    site_section5: '<site_section5>',
  },
  user_data: {
    user_id: '<user_id>',
    user_login_state: '<user_login_state>',
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|brand|string|required|The brand the site is associated with.|neutrogena|
|country|string|required|The country the site is associated with.|us|
|language|string|required|The language of the current page, usually pulled from the `<html>` tag `lang` attribute.|en|
|event_specific_category|string|recommended|Used for grouping pages (or screens) into categories based on their content. Most often aligns with page tags/taxonomy terms or breadcrumbs.|sun protection|
|event_specific_category[2-5]|string|optional|Used for grouping pages (or screens) into subcategories based on their content. Most often aligns with page tags/taxonomy terms or breadcrumbs.|waterproof|
|event_specific_id|string|recommended|A durable identifier for a page that will enable measurement over time despite the page URL, title, etc changing. Generally sourced from the site content management system.|12345|
|event_specific_name|string|optional|A unique name for this page independent of page title. Google does not tend to use custom page names, but it's a mainstay in Adobe and therefore is included here for compatibility as well as for its usefulness generally.|homepage,search results,product:neutrogena hydro boost gel|
|event_specific_type|string|recommended|Used for grouping pages (or screens) into high level types.|article,blog,homepage,product|
|page_location|string|required|The url of the page currently being viewed.|https://www.neutrogena.com|
|page_referrer|string|required|The previous page URL, generally available in `document.referrer`|https://www.neutrogena.com|
|page_title|string|required|The title of the page currently being viewed, generally available in the HTML `<title>` tag; alternatively, the low-level, client-defined name of the page currently being viewed.|homepage,search results,product:neutrogena hydro boost gel|
|region|string|required|The region the site is associated with.|EMEA|
|site_section|string|recommended|The section of the site that the current page resides in.|products|
|site_section[2-5]|string|recommended|The subsections of the site that the current page resides in.|sun protection products|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|
