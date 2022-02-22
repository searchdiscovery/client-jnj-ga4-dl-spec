# Menus

Add the attribute below to each `<li>` within a menu component block.

This attribute will enable the construction of a link heirarchy for menu items.

## HTML Data Attributes

```html
<li
  data-layer-menu_item="<menu_item>"
>
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|menu_item|string|required|The text of the link contained within the `<a>` tag inside of the `<li>`|Contact Us|