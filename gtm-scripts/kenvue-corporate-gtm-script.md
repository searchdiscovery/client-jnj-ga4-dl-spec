# Kenvue Corporate GTM Coode
This document is a quick reference to implement the Global GTM Container across all Kenvue Corporate sites. For any questions regarding this content please contact Steven Rowe - srowe32@its.jnj.com

## Javascript Code
Add the following code to the site, as high inside the tag as possible:

```js
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-PL7ZQG9');</script>
<!-- End Google Tag Manager -->
