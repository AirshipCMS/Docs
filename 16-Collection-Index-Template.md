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

### Property: `params`

### Property: `items`

---

## Properties Rendered inside `items`
For a list of all `properties` and `fields` that can be rendered within the list of items, see the docs for the collection [`show.html`](/documentation/view/collection-show-template) template. Any `properties` and `fields` listed as renderable on the `show.html` template can be rendered on the `index.html` template when wrapped in an `{{#each items}}` or `{{#sort_list}}` helper.

## Limitations to items rendered on `index.html`
- any items in the collection that are in _Draft Mode_ will not render on the template.
- items exceeding the [`Collection Limit`](#) set in the Airship CMS Admin will not render on the template. Pagination should be used to create links to additonal pages of content in the collection.
- if any items contain _Related_ type datafields, the related fields data will not render on the `index.html` template.

!! LEFT OFF HERE !!

### Items `aerostat_collection`
These properties can also be accessed directly from the [collection](#property-collection) property.

The following examples show how to render each property from the item aerostat_collection field:

#### Property: `id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
{{#each items}}
<p>{{aerostat_collection.id}}</p>
{{/each}}
```

Example Output:
```
<p>305</p>
<p>305</p>
```


#### Property: `public_path`
This is the identifier for the item's collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
{{#each items}}
<p>{{aerostat_collection.public_path}}</p>
{{/each}}
```

Example Output:
```
<p>mammals</p>
<p>mammals</p>
```


### Items `categories`
To use these properties, categories must be enabled in the Admin panel for the collection. The following examples show how to render the available categories properties for each item:


#### Property: `id`
This is the ID of the category.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>320</p>
<p>319</p>
```

#### Property: `title`
This is the category name.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{title}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Common</p>
<p>Fluffy</p>
```

#### Property: `permalink`
The permalink is the identifier for the category following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{permalink}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>common</p>
<p>fluffy</p>
```


#### Property: `fields`
Example Markup:
Example Output:


#### Property: `aerostat_collection_id`
This is the ID of the collection given by Airship CMS.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{aerostat_collection_id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>305</p>
<p>305</p>
```

#### Property: `created_at`
This is the timestamp of when the category was created.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{format_date created_at "r" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Wed, 17 May 2017 04:02:26 GMT</p>
<p>Wed, 17 May 2017 04:02:10 GMT</p>
```

#### Property: `updated_at`
This is the timestamp of when the category was last updated.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-30 06:22:59Z</p>
```


#### Property: `sorting_position`
This is the value of the category's sorting position.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{sorting_position}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>1</p>
<p>0</p>
```

### Items `tags`
To use these properties, tags must be enabled in the Admin panel for the collection. The following examples show how to render the available tag properties for each item:


#### Property: `id`
This is the ID of the tag given by Airship CMS.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>572</p>
<p>593</p>
```


#### Property: `site_id`
This is the ID of the website that the tag belongs to.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{site_id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>62</p>
<p>62</p>
```


#### Property: `name`
This is the tag name.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{name}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>carnivore</p>
<p>fluffy</p>
```


#### Property: `created_at`
This is the timestamp of when the tag was created.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{format_date created_at "o" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24T06:15:52.6890000+00:00</p>
<p>2017-05-17T04:02:03.1730000+00:00</p>
```

#### Property: `updated_at`
This is the timestamp of when the tag was updated.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-17 04:02:03Z</p>
```

## Property: `collection`
The following properties and fields are available on the index.html's `collection` property:


### Property: `id`
This is the collection's id.

Example Markup:
```
<p>{{collection.id}}</p>
```

Example Output:
```
<p>305</p>
```


### Property: `site_id`
This is the id of the website given by Airship CMS.

Example Markup:
```
<p>{{collection.site_id}}</p>
```

Example Output:
```
<p>62</p>
```


### Property: `title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.title}}</p>
```

Example Output:
```
<p>Mammals</p>
```


### Property: `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.name}}</p>
```

Example Output:
```
<p>mammals</p>
```


### Property: `public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{collection.public_path}}</p>
```

Example Output:
```
<p>mammals</p>
```


### Property: `has_public_make`
This shows whether or not public make is enabled for the current collection. The public make setting can be enabled/disabled in the Modify panel in Admin.

Public make must be enabled for user submissions, such as creating new Contact items within a Sign Up collection via sign up form. 

Example Markup:
```
<p>{{collection.has_public_make}}</p>
```

Example Output:
```
<p>false</p>
```


### Property: `has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

### Property: `has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

### Property: `has_comments`
Example Markup:
```
<p>{{collection.has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

### Property: `has_publish_date`
Example Markup:
```
<p>{{collection.has_publish_date}}</p>
```

Example Output:


### Property: `show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```


### Property: `layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{collection.layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

### Property: `primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```


### Property: `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```


### Property: `has_plans`
Example Markup:
```
<p>{{collection.has_plans}}</p>
```

Example Output:
```
<p>false</p>
```

---

## Properties you can't access from the `index.html` template
Data from X will not render with Airship Propellers. Alternatively, if you want to render content that exists outside of the page, you can do an Airship API call and render the content with a script.
