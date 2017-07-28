# Collection `show.html` template:
The `show.html` template renders a single item in a collection. The url for a post is a collection follows the format: `/collection-public-path/view/item-permalink`.

The collection `show.html` template may contain html markup and Collection Propellers markup that renders site content. This template is not generated with any pre-defined markup in order to give developers the most flexibility when structuring content for this page.


## Location & Setup
The `show.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `show.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── show.html
```

---

See [Collection Templates](/documentation/view/collection-templates) for more information on how to set the collection template directory for a collection.

When you are developing locally the url of the show page will be `localhost:9001/public_path/view/item-permalink`, where `public_path` is the value you set for the collection in Airship CMS, and `view` is added automatically and cannot be customized.

In this example the public_path for the Blog collection was set to `blog`, and the item's permalink is `introduction`, so the full url is `localhost:9001/blog/view/introduction`. When you navigate to this url, you should see the contents of the `show.html` collection template rendered in the browser.

---

## Collection `show.html` Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On the collection `show.html`, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with the `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access. The [#sort_list](/documentation/view/propeller-helpers#user-content-sort_list) helper may also be used in place of the `{{#each}}` helper.

## Collection `show.html` Properties:
The following properties can be rendered on the `show.html` template:

### `params`

### `aerostat_collection`

### `tags`

### `categories`

### `related_items`

For more information about these properties, their available fields, and other general properties, check out the [Collection Item Properties](/documentation/view/collection-item-properties) docs.

---

## Data rendered on the `show.html` template
For a list of all `properties` and `fields` that can be rendered within the `show.html` template, see the docs for [Collection Item Properties](/documentation/view/collection-item-properties).

Items must be _published_ in order to be renderable. To publish an item in a collection, navigate to the Edit Item page in the Admin portal at `yoursubdomain.airshipcms.io/admin`, click the `Draft Item` switch at the right of the page, select a publish date, then save the item. Note that the item will not be considered published and renderable until on or after the selected publish date.
