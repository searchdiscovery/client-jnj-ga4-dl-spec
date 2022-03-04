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
    category: '<category>',
    category2: '<category2>',
    category3: '<category3>',
    category4: '<category4>',
    category5: '<category5>',
    identifier: '<identifier>',
    language: '<language>',
    page_location: '<page_location>',
    page_name: '<page_name>',
    page_referrer: '<page_referrer>',
    page_title: '<page_title>',
    page_type: '<page_type>',
    region: '<region>',
    site_section: '<site_section>',
    site_section2: '<site_section2>',
    site_section3: '<site_section3>',
    site_section4: '<site_section4>',
    site_section5: '<site_section5>',
    user_login_state: '<user_login_state>',
  },
  user_data: {
    user_id: '<user_id>',
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|brand|string|required|The brand the site is associated with.|neutrogena|
|country|string|required|The country the site is associated with.|us|
|language|string|required|The language of the current page, usually pulled from the `<html>` tag `lang` attribute.|en|
|category|string|recommended|Used for grouping pages (or screens) into categories based on their content. Most often aligns with page tags/taxonomy terms or breadcrumbs.|sun protection|
|category[2-5]|string|optional|Used for grouping pages (or screens) into subcategories based on their content. Most often aligns with page tags/taxonomy terms or breadcrumbs.|waterproof|
|identifier|string|recommended|A durable identifier for a page that will enable measurement over time despite the page URL, title, etc changing. Generally sourced from the site content management system.|12345|
|page_location|string|required|The url of the page currently being viewed.|https://www.neutrogena.com|
|page_name|string|optional|A unique name for this page independent of page title. Google does not tend to use custom page names, but it's a mainstay in Adobe and therefore is included here for compatibility as well as for its usefulness generally.|homepage,search results,product:neutrogena hydro boost gel|
|page_referrer|string|required|The previous page URL, generally available in `document.referrer`|https://www.neutrogena.com|
|page_title|string|required|The title of the page currently being viewed, generally available in the HTML `<title>` tag; alternatively, the low-level, client-defined name of the page currently being viewed.|homepage,search results,product:neutrogena hydro boost gel|
|page_type|string|recommended|Used for grouping pages (or screens) into high level types.|article,blog,homepage,product|
|region|string|required|The region the site is associated with.|EMEA|
|site_section|string|recommended|The section of the site that the current page resides in.|products|
|site_section[2-5]|string|recommended|The subsections of the site that the current page resides in.|sun protection products|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|authenticated, anonymous|
