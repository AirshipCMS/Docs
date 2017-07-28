# Collection `categories.html` Template:
The `categories.html` template is used as an index for all categories within a collection. The url for the categories in a collection follows the format: `/collection-public-path/categories`.

The collection `categories.html` template may contain html markup and Collection Propellers markup that renders site content. This template is not generated with any pre-defined markup in order to give developers the most flexibility when structuring content for this page.


## Location & Setup
To use this page, categories must be enabled within the collection. Categories can be enabled at anytime. To enable categories, click the checkbox for `Has Categories` within the `Collection Settings` section in the `New Collection` or `Modify Collection` pages in the Admin portal.

The `categories.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `categories.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── categories.html
```

---

See [Collection Templates](/documentation/view/collection-templates) for more information on how to set the collection template directory for a collection.

When you are developing locally the url of the categories page will be `localhost:9001/public_path/categories`, where `public_path` is the value you set for the collection in Airship CMS.

In this example, the public_path for the Blog collection was set to `blog`, so the full url is `localhost:9001/blog/categories`. When you navigate to this url, you should see the contents of the `categories.html` collection template rendered in the browser.

---

## Collection `categories.html` Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On the collection `categories.html`, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with the `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access. The [#sort_list](/documentation/view/propeller-helpers#user-content-sort_list) helper may also be used in place of the `{{#each}}` helper.

## Collection `categories.html` Properties:
The following properties can be rendered on the `categories.html` template:

### `categories`

For more information about this property and its available fields, check out the [Collection Item Properties](/documentation/view/collection-item-properties) docs.

---

## Data rendered on the `categories.html` template
For a list of all `properties` and `fields` that can be rendered within the `categories.html` template, see the docs for [Collection Item Properties](/documentation/view/collection-item-properties).

This page does not have access to data for items within the collection.
