# Collection `index.html` Template
The `index.html` template is used to display all items within a collection.
The public path of the collection, e.g. `/blog`, routes to this page.

The collection `index.html` template may contain html markup and Collection Propellers markup that renders site content. This template is not generated with any pre-defined markup in order to give developers the most flexibility when structuring content for this page.

## Location in your local directory
The `index.html` template for a collection should be located in the appropriate subdirectory within the `templates` directory. For a collection named `blog`, the `index.html` template location would be:
```
compartments
.
└── templates
    └── blog
        └── index.html
```

---

## Setting a Collection Template Directory in Airship CMS
See [Collection Templates](/documentation/view/collection-templates) for more information on how to set the collection template directory for a collection.

## Viewing the Collection index locally
In Airship CMS, in the `Collection Setup` section of the collection you want to view locally, check that the `Public Path` is written exactly as you want it to appear when someone navigates to your page.

![collection-setup](https://user-images.githubusercontent.com/1865400/28496774-534f94a2-6f0f-11e7-9a13-8128c1d827bf.png)

When you are developing locally, the url of the index will be `localhost:9001/pubic_path`, where `pubic_path` is the value you set for the collection in Airship CMS. In this example, the public_path for the Blog collection was set to `blog` so the full url is `localhost:9001/blog`. When you navigate to this url, you should see the contents of the `index.html` collection template rendered in the browser.

---

## Collection index Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On the collection `index.html`, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access.

## Collection Properties:
The following properties can be rendered on the `index.html` template:

### `params`

### `collection`

### `{{#each items}}`

---

# Data rendered inside `{{#each items}}`
For a list of all `properties` and `fields` that can be rendered within `{{#each items}}`, see the docs for the collection [`show.html`](/documentation/view/collection-show-template) template. All `properties` and `fields` listed as renderable on the `show.html` template can be rendered on the `index.html` template when wrapped in an `{{#each items}}` or `{{#sort_list}}` helper.

## Not renderable inside `{{#each items}}`
- any items in the collection that are in _Draft Mode_ will not render on the template.
- items exceeding the [`Collection Limit`](#) set in the Airship CMS Admin will not render on the template. Pagination should be used to create links to additonal pages of content in the collection.
- if any items contain _Related_ type datafields, the related fields data will not render on the `index.html` template.

## Additional Properties inside `{{#each items}}`
The following properties are renderable on the `index.html` template, though not necessarily available on the `show.html` template:

### `aerostat_collection.id`

### `aerostat_collection.public_path`

### `categories`

### `tags`

---

## Properties you can't access from the `index.html` template
Data from X will not render with Airship Propellers. Alternatively, if you want to render content that exists outside of the page, you can do an Airship API call and render the content with a script.
