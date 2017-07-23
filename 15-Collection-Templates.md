# Collection Templates
Collection Templates include a pre-determined set of the following templates: [`index.html`](/documentation/view/collection-index-template), [`show.html`](/documentation/view/collection-show-template), [`categories.html`](/documentation/view/collection-categories-template), and [`category.html`](/documentation/view/collection-category-template). 

Collection Templates may contain html markup plus Airship Page Propellers code that renders content from the Airship CMS admin portal. By design, collection templates do not contain pre-defined markup. This gives developers the most flexibility when structuring content within the collection.

## Rendering Items
Items in collections *must* be published in order for them to render on collection templates.

## Collection Templates in your local directory
Whenever you create a collection, the corresponding set of collection templates can be generated in the CMS and downloaded, or manually created in your local project directory.

Using either creation method, the collection template directory is saved in the `/compartments/templates/ directory` containing `index.html`, `show.html`, `categories.html`, and `category.html`, as needed. Here is an example of a local project directory with a `blog` collection:
```
compartments
.
└── templates
    ├── root.html
    └── blog
        ├── categories.html
        ├── category.html
        ├── index.html
        └── show.html
```

## `index.html` template:
The `index.html` template is used to display all items within a collection.
The public path of the collection, e.g. `/blog`, routes to this page.

Check out the docs for rendering [`index.html`](/documentation/view/collection-index-template), and all available properties and fields that can be accessed from this template.

## `show.html` template:
The `show.html` template renders a single item in a collection.
The url for a post is a collection follows the format: `/collection-public-path/view/item-permalink`.

Check out the docs for rendering [`show.html`](/documentation/view/collection-show-template), and all available properties and fields that can be accessed from this template.


## `categories.html` template:
The `categories.html` template is used as an index for all categories within a collection.
The url for the categories in a collection follows the format: `/collection-public-path/categories`.

Check out the docs for rendering [`categories.html`](/documentation/view/collection-categories-template), and all available properties and fields that can be accessed from this template.

## `category.html` template:
The `category.html` template is used as an index for a sinle category within a collection.
The url for a category in a collection follows the format: `/collection-public-path/categories/category-permalink`.

Check out the docs for rendering [`category.html`](/documentation/view/collection-category-template), and all available properties and fields that can be accessed from this template.
