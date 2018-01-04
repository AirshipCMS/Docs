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
There are no excluded properties on the `show.html` template.
