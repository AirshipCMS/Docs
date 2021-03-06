# Collection `category.html` Template:
The `category.html` template is used as an index for a single category within a collection. The url for a category in a collection follows the format: `/collection-public-path/categories/category-permalink`.

The collection `category.html` template may contain html markup and Collection Propellers markup that renders site content. This template is not generated with any pre-defined markup in order to give developers the most flexibility when structuring content for this page.

## Location & Setup
To use this page, categories must be enabled within the collection.

Categories can be enabled at anytime. To enable categories, click the checkbox for `Has Categories` within the `Collection Settings` section in the `New Collection` or `Modify Collection` pages in the Admin portal. To add items to categories, select all that apply within the `Category` dropdown at the right of the Create/Edit Item page.

The `category.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `category.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── category.html
```

---

See [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more information on how to set the collection template directory for a collection.

When you are developing locally the url of the category page will be `localhost:9001/public_path/categories/category-permalink`, where `public_path` is the value you set for the collection in Airship CMS.

In this example, the public_path for the Blog collection was set to `blog`, and the permalink of the category was set to `design`, so the full url is `localhost:9001/blog/categories/design`. When you navigate to this url, you should see the contents of the `category.html` collection template rendered in the browser.

---

## Collection `category.html` Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On the collection `category.html`, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with the `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access. The [#sort_list](https://airshipcms.io/documentation/view/propeller-helpers#user-content-sort_list) helper may also be used in place of the `{{#each}}` helper.

## Collection `category.html` Properties:
The following properties can be rendered on the `categories.html` template:

- `params` [index--params]
- `items [list]` [each--items]
- `collection` [index--collection]
- `category` [category--category]

---

## Data rendered inside `{{#each items}}` on the `category.html` template
For a list of all `properties` and `fields` that can be rendered within `{{#each items}}`, see the docs for `Collection Item Properties`. Most `properties` and `fields` renderable on the `show.html` template can be rendered on the `category.html` template when wrapped in an `{{#each items}}` or `{{#sort_list}}` helper (see below for exceptions).

### Not renderable inside `{{#each items}}` on the `category.html` template
- any items in the collection that are in _Draft Mode_ will not render on the template.
- items exceeding the [`Collection Limit`](#) set in the Airship CMS Admin will not render on the template. Pagination should be used to create links to additonal pages of content in the collection.
- if any items contain _Related_ type datafields, the related fields data will not render on the `category.html` template.
