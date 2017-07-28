# Collection Item Properties
Description. The following are properties available for Items within in a Collection.

---

The following properties can be rendered for items on a collection `show.html` template, or within an `each` block on the collection `index.html`, collection `category.html`, or if the items are in a `related` block:
- `params`
- `id`
- `aerostat_collection_id`
- `permalink`
- `product_title` (if the item is a product)
- `fields` (see below for field types)
- `sorting_position`
- `published_on`
- `created_at`
- `updated_at`
- `aerostat_collection`
- `tags [list]` (if tags are enabled)
- `categories [list]` (if categories are enabled)
- `product_variations[list]` (if the item is a product)
- `related_items [list]` (only renders on `show.html`)
- `slug`

The following fields can be rendered for items on a collection `show.html` template, or within an `each` block on the collection `index.html`, collection `category.html`, or if the items are in a `related` block:
- `text`
- `textarea`
- `richtext area`
- `image`
- `link`
- `number`
- `radio`
- `select`
- `multiselect`
- `checkbox`
- `list of images`
- `list of links`
- `date`
