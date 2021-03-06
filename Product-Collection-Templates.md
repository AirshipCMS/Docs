# Product Collection Templates
Product Collection Templates include the following pages: index.html, show.html, categories.html, and category.html. They are similar to [Collection Templates](Collection-Templates.md), though have properties that are specifically for collections.

Items in the collection _must_ be published to be available for rendering.

Check out the [Collections](Collections.md) documentation for more information about collections.



## Template filenames
For each collection, within the `/compartments/templates/` directory, there should be a directory with the name chosen in Admin.

The filenames within these collection directories should be exactly index, show, categories, and category with the `html` extension.

Example collection directory:
```
compartments
.
└── templates
    ├── root.html
    └── collection-subdir
        ├── categories.html
        ├── category.html
        ├── index.html
        └── show.html
```

## `index.html` template:
The index.html template is used to display all items within a collection.

The public path of the collection, e.g. `/blogs`, routes to this page.

Check out the [index.html product page documentation](Product-Collection-Index-Template.md) for all available properties and fields, and examples of how to render them.



## `show.hmtl` template:
The show.html template is used for pages that focus on one specific item in the collection.

The path for this page is `/collection-public-path/view/item-permalink`.

Check out the [show.html product page documentation](Product-Collection-Show-Template.md) for all available properties and fields, and examples of how to render them.



## `categories.html` template:
The categories.html template is used as an index for all categories in a collection. This page has information about each category within the collection.

The path for this page is /collection-public-path/categories.

Check out the [categories.html product page documentation](Product-Collection-Categories-Template.md) for all available properties and fields, and examples of how to render them.



## `category.html` template:
The category.html template is used as an index for one specific category in a collection. This page shows all items within a certain category in the collection.

The path for this page is `/collection-public-path/categories/category-permalink`.

Check out the [category.html product page documentation](Product-Collection-Category-Template.md) for all available properties and fields, and examples of how to render them.
