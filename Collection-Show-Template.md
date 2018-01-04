# Collection `show.html` template:
The `show.html` template renders a single item in a collection. The url for a post is a collection follows the format: `/collection-public-path/view/permalink`.

## Location & Setup
The `show.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `show.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── show.html
```

See [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more information on how to set the collection template directory for a collection.

## Renderable Properties
See [Collection Item Properties](https://airshipcms.io/documentation/view/collection-item-properties) for the full list of properties and fields renderable on the `show.html` template.

## Excluded Properties
Data from pages or other collections will not render on a collection, unless a relationship is created with a "related datafield." Alternatively, if you want to render content that exists outside of the collection, you can do an Airship API call and render the content with a script.
