---
title: 'Home'
---

# Johnson and Johnson GA4 Data Layer and Data Attribute Spec

## Overview
This repository contains the necessary specifications to build an Event Driven Data Layer.

## Events
Each file inside the **[events](events)** folder corresponds to a single use case or site event that needs to be implemented.

These will be used to share data with Google Tag Manager on desktop and will be sent directly to Google Analytics 4 on mobile.

## Data Attributes
Custom HTML data attributes enable some data layer events to be fired without developers having to write Javascript to fire them. They are added to the HTML source code on specific page elements so that interactions with those elements can be tracked. They are most often used for custom click events, though they can also be used for hover events, form field changes, form submissions, and many other similar Javascript events.

### Region and component attributes
These attributes are unique in that they are used by all data attribute events. They should be applied to the HTML elements for each component and region of the site of the page/site that needs to be tracked. 

For instance, the main page `<header>` tag might have the `data-layer-region="header"` attribute added to it, while a tabset might have `data-layer-component="tabset"`. Any data layer events that are triggered via interactions with child HTML elements under the `<header>` or tabset would include these contextual attributes. 

See the **[data-attributes](data-attributes)** folder for detailed implementation guidelines.

## Questions/Comments
For any questions or comments, please contact charlie.tysse@searchdiscovery.com.