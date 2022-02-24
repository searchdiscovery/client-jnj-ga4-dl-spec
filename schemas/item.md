# Item Object

An `item` is how GA4 refers to a product.  An item object should be sent whenever a product is displayed, selected, added to a cart, or purchased.

## Object format

```json
{
  // Global
  "affiliation": "<affiliation>",
  "currency": "<currency>",
  "gtin": "<gtin>",
  "item_brand": "<item_brand>",
  "item_category": "<item_category>",
  "item_id": "<item_id>",
  "item_name": "<item_name>",
  "item_variant": "<item_variant>",
  "price": "<price>",
  "quantity": "<quantity>",
  "sku": "<sku>",

  // Contextual
  "coupon": "<coupon>",
  "discount": "<discount>",
  "creative_name": "<creative_name>",
  "creative_slot": "<creative_slot>",
  "item_list_id": "<item_list_id>",
  "item_list_name": "<item_list_name>",
  "index": "<index>",
  "location_id": "<location_id>",
  "promotion_id": "<promotion_id>",
  "promotion_name": "<promotion_name>",
  "item_subscription_type": "<promotion_id>"
}
```

## Variable definitions
|Name|Type|Required|Description|Example Value|
| --- | --- | --- | --- | --- |
|affiliation|string|recommended|A product affiliation to designate a supplying company or brick and mortar store location.|Google Store|
|coupon|string|contextual|Coupon code used for a purchase.|SUMMER_FUN|
|creative_name|string|recommended if item is being sent with a promotion event|The name of a creative used in a promotional spot.|summer_banner2|
|creative_slot|string|recommended if item is being sent with a promotion event|The name of a creative slot.|featured_app_1|
|currency|string|recommended|The currency, in 3-letter ISO 4217 format.|USD|
|discount|number|conditional|Monetary value of discount associated with a purchase.|2.22|
|gtin|string|recommended|A Global Trade Item Number (GTIN). GTINs identify trade items, including products and services, using numeric identification codes. UPCs are a type of GTIN, so they should be added via this parameter.|012345678905|
|index|number|conditional|The index/position of the item in a list.|2|
|item_brand|string|recommended|Item brand|Gucci|
|item_category|string|recommended|Item Category (context-specific). `item_category2` through `item_category5`can also be used if the item has many categories.|pants|
|item_id|string|required|Item ID (context-specific).|SKU_12345|
|item_list_id|string|contextual|The computer-readable machine name of the list the item showed up in (if sent with a view_item_list event). Use UUID provided by the component if no more specific ID is available.|12345abcde12345|
|item_list_name|string|contextual|The human-readable name of the item list the item showed up in (if sent with a view_item_list event). If one is not available, populate with numerical index of which list this is on the page (1-indexed). For `filter_by_group` component, use that value.|filter_by_group, recommended_products, recently_viewed_products|
|item_name|string|required|Item Name (context-specific).|jeggings|
|item_subscription_type|string|recommended|Item Subscription Type. The subscription type when a user chooses to subscribe to a product being sent multiple times after their purchase.|3-months, 6-months, 9-months|
|item_variant|string|recommended|The variant of the item.|Black|
|location_id|string|recommended if the item is associated with a physical location|The location associated with the event. If possible, set to the Google Place ID that corresponds to the associated item. Can also be overridden to a custom location ID string.|L_12345|
|price|number|recommended|The monetary price of the item, in units of the specified currency parameter.|9.99|
|promotion_id|string|either `promotion_id` or `promotion_name` is required if item is being sent with a promotion event|The ID of a product promotion. |P_12345|
|promotion_name|string|either `promotion_id` or `promotion_name` is required if item is being sent with a promotion event|The name of a product promotion. One of `promotion_id` or `promotion name` is required.|Summer Sale|
|quantity|integer|recommended|Item quantity.|1|
|sku|string|recommended|The Stock Keeping Unit (SKU), i.e. a merchant-specific identifier for a product or service|7702031413424|