# Collection Item Properties
The following are properties available for an item within in a collection. 

## Renderable Properties
The following properties will render on the `show.html` template or within an `{{#each}}` block on the collection `index.html` or collection `category.html` template:

- `params` [index--params]
- `id` [each--id]
- `aerostat_collection_id` [each--aerostat_collection_id]
- `permalink` [each--permalink]
- `product_title` (if the item is a product) [each--product_title]
- `sorting_position` [each--sorting_position]
- `published_on` [each--published_on]
- `created_at` [each--created_at]
- `updated_at` [each--updated_at]
- `aerostat_collection` [index--aerostat_collection]
- `tags [list]` (if tags are enabled) [index--tags]
- `categories [list]` (if categories are enabled) [index--categories]
- `product_variations[list]` (if the item is a product) [index--product_variations]
- `slug` [each--slug]
- `related_items[list]` (if the item has related items) ???

## Renderable Datafields
Datafields are also renderable for an item within in a collection. For a list of datafields that will render on the `show.html` template or within an `{{#each}}` block on the collection `index.html` or collection `category.html` template, see [Datafields](https://airshipcms.io/documentation/view/datafields)

---

Note 1/3/2018: Remove all fields. Add Related Items to Properties.
