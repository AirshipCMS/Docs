# Collection Templates
Items in collections *must* be published to be available for rendering.

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

## `index.hmtl` template:
The following properties and fields can be rendered on the index.html template:

### Property: `params`
These fields are for pagination.

Example markup using the `{{create_page_query}}` helper with fields from `params` to create a query string for pagination:
```
<li><a href="{{create_page_query page='1' sort='permalink' order='asc' limit='15'}}">Mammals</a></li>
```

Example Output HTML:
```
<li><a href="?page=1&amp;limit=15&amp;sort=permalink&amp;order=asc">Mammals</a></li>
```

Example Output Query String:
```
/mammals?page=1&limit=15&sort=permalink&order=asc
```

For more info about pagination, see the documentation on the [create_page_query helper](Propeller-Helpers.md#create_page_query).

### Property: `items`

### Property: `collection`


## `show.html` template:
- fields and accessible properties.

## `categories.hmtl` template:
- fields and accessible properties.

## `category.html` template:
- fields and accessible properties.
