# Collection `index.html` Template
The `index.html` template is used to display a list of items within a collection. 

The url for the `index.html` is the `public_path` of the collection (such as `/blog`).

## Template Setup
The `index.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `index.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── index.html
```

See [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more information on how to automatically generate or manually create a set of collection templates for a collection.

## Renderable Properties
The following properties can be rendered on the `index.html` template:

- `params` [index--params]
- `items [list]` [each--items]
- `collection` [index--collection]

## Property: items
Within an `{{#each items}}` propeller, collection item `properties` and `fields` can be rendered as a list. See [Collection Item Properties](https://airshipcms.io/documentation/view/collection-item-properties) for the full list of renderable properties and fields. 

## Excluded Properties
- items in the collection that are in Draft Mode will not render on the `index.html` template.
- items exceeding the Collection Limit that is set in the Airship CMS Admin will not render on the `index.html` template.
- `related_items` data attached to items will not render on the `index.html` template.
