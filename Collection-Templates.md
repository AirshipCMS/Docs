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

For more info about pagination, see the documentation on the [create_page_query helper](Propeller-Helpers.md#create_page_query).

Example markup using the `{{create_page_query}}` helper with fields from `params` to create a link with a query string for pagination:
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


### Property: `items`
Each item in the collection can be accessed through the items property.

The following examples show how to render each property or field in items:

#### Property: `id`
Example Markup:
```
<p>{{id}}</p>
```

Example Output:
```
<p>3449</p>
```


#### Property: `aerostat_collection_id`
Example Markup:
```
<p>{{aerostat_collection_id}}</p>
```

Example Output:
```
<p>305</p>
```


#### Property: `permalink`
Example Markup:
```
<p>{{permalink}}</p>
```

Example Output:
```
<p>anteater</p>
```


#### Property: `sorting_position`
Example Markup:
```
<p>{{sorting_position}}</p>
```

Example Output:
```
<p>37</p>
```


#### Property: `published_on`
This is the timestamp of when the current item was published. The publish date can be set in the Admin panel. The timestamp can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date published_on "r" "us"}}</p>
```

Example Output:


#### Property: `created_at`
This is the timestamp of when the current item was created. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date created_at "o" "us"}}</p>
```

Example Output:
```
<p>2017-05-17T07:01:45.994Z</p>
```


#### Property: `updated_at`
This is the timestamp of when the current item was last updated. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date updated_at "u" "us"}}</p>
```

Example Output:
```
<p>2017-05-24T06:15:52.647Z</p>
```

#### Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain.

Example Markup:
```
<p>{{slug}}</p>
```

Example Output:
```
<p>/mammals/view/anteater</p>
```

#### Item Fields
The content endered in the Admin panel for each item is accessible through the item's `fields` property. These fields are similar to (Page fields)[Page-Templates.md#page-fields], though the related_items field for each item is not available within the collection index.html. 

For fields that contain HTML content, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](#field-type-image), [link](#field-type-link), or [related aerostats](#field-type-related-aerostats).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](#field-type-list-of-images) or [list of links](#field-type-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](Propeller-Helpers.md#sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

The following examples show how to render the content from each field type on items:


#### Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `name`:
```
<h1>{{fields.name}}</h1>
```

Example Output:
```
<h1>Anteater</h1>
```


#### Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `short_description`:
```
<p>{{fields.short_description}}</p>
```

Example Output:
```
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
```


#### Field Type: `rich text area`
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `description`:
```
<div>{{{fields.description}}}</div>
```

Example Output:
```
<div><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.<br>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p></div>
```


#### Field Type: `image`
Example markup using an image field the variable name `animal_ige`:
```
{{#each fields.animal_image}}
<div class="animal-image">
  <h6>{{title}}</h6>
  <p>{{subtitle}}</p>
  <img src="{{url}}" alt="">
  <p>{{caption}}</p>
</div>
{{/each}}
```

Example Output:
```
<div class="animal-image">
  <h6>Grumpy Hedgie</h6>
  <p>Lorem ipsum dolor</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/hedgietest_rpaxih.jpg" alt="">
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```


#### Field Type: `link`
Aside from links, this field is useful for simple text content as it provides more control over how the content is rendered than other text fields.

For example, the link field allows each (optional) `title`, `subtitle`, `url`, and `caption` content to be rendered as separate elements, while the textarea field renders all content within the same HTML element by default.

Example markup using a link field with the variable name `resource_link`:
```
<div class="link">
  {{#each fields.resource}}
  <a href="{{url}}">Resource: {{title}}</a>
  <p>{{subtitle}}</p>
  <p>{{caption}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshpcms.io">Resource: Lorem ad voluptatibus amet fugit excepturi facilis?</a>
  <p>Lorem ad voluptatibus amet</p>
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
```


#### Field Type: `number`
Example markup using a number field with the variable name `population_size`:
```
<p>Population Size: {{fields.population_size}}</p>
```

Example Output:
```
<p>Population Size: 100,000</p>
```


#### Field Type: `radio`
Example markup using a radio field with the variable name `is_endangered`:
```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:
```
<p>Endangered: No</p>
```


#### Field Type: `select`
Example markup using a select field with the variable name `animal_kingdom`:
```
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:
```
<p>Animal Kingdom: Animals</p>
```


#### Field Type: `multiselect`
While the multiselect field can be rendered the same way as other `[list]` notated fields, it can also be rendered as a comma separated list for simplicity.

Example markup using a multiselect field with the variable name `things`:
```
<div class="all-the-things">
  {{#each fields.thing}}
  <p>{{this}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="all-the-things">
  <p>Thing 2</p>
  <p>Thing 1</p>
</div>
```

Example markup rendering the multiselect field as a comma separated list:
```
<p>{{fields.thing}}</p>
```

Example Output:
```
<p>Thing 2,Thing 1</p>
```


#### Field Type: `checkbox`
Example markup using a checkbox with the variable name `show_image`:
```
<div>
  {{#if fields.show_image}}
    <h3>Hedgehog</h3>
    {{#each fields.animal_image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image for this animal.</h3>
  {{/if}}
</div>
```

Example Output if `show_image` was checked:
```
<div>
    <h3>Hedgehog</h3>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/hedgietest_rpaxih.jpg" alt="">
</div>
```

Example Output if `show_image` was not checked:
```
<div>
    <h3>Sorry! No image for this animal.</h3>
</div>
```


#### Field Type: `list of images`
Example markup using a list of images with the variable name `additional_images`:
```
<div class="image-container">
  {{#each fields.additional_images}}
    <div class="image">
      <h6>{{title}}</h6>
      <img src="{{url}}" alt="">
      <p>{{subtitle}}</p>
      <p>{{caption}}</p>
    </div>
  {{/each}}
</div>
```

Example Output:
```
<div class="image-container">
    <div class="image">
      <h6>Grump</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/hedgietest_bwkvdi.jpg" alt="">
      <p>grumpy hedgie</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
    <div class="image">
      <h6>Dino</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993552/media/hedgietest2_clixqs.jpg" alt="">
      <p>dino hedgie</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
</div>
```

Example markup rendering the list of images using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="sorted-images">
  {{#sort_list fields.additional_images sort="title" order="desc"}}
    <div class="image">
      <h6>{{title}}</h6>
      <img src="{{url}}" alt="">
      <p>{{subtitle}}</p>
      <p>{{caption}}</p>
    </div>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="image-container">
  <div class="image">
    <h6>Grump</h6>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/hedgietest_bwkvdi.jpg" alt="">
    <p>grumpy hedgie</p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
  <div class="image">
    <h6>Dino</h6>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494993552/media/hedgietest2_clixqs.jpg" alt="">
    <p>dino hedgie</p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
</div>
``` 


#### Field Type: `list of links`
Example markup using a list of links with the variable name `additional_resource_links`:
```
<div class="additional-links">
  {{#each fields.additional_resource_links}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
  </div>
  {{/each}}
</div>
```

Example Output:
```
<div class="additional-links">
    <div class="link">
      <a href="http://marketing.airshipcms.io">Resource: Title</a>
      <p>sub</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
    <div class="link">
      <a href="http://marketing.airshipcms.io">Resource: Other</a>
      <p>other sub</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
</div>
```

Example markup rendering the list of links using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="additional-links">
  {{#sort_list fields.additional_resource_links sort="title" order="desc"}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
  </div>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: other link</a>
    <p>Lorem ipsum dolor rem nam sequi ea</p>
    <p>Lorem ipsum dolor rem nam sequi ea dolor voluptatibus ullam eius. Odit a alias fuga voluptatibus ex ab architecto ipsa? Aut adipisci iusto quia quibusdam rem dicta voluptates, placeat similique quas minima!</p>
  </div>
  <div class="link">
    <a href="http://marketing.airshipcms.io/">Resource: link</a>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio</p>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
  </div>
</div>
```


#### Field Type: `date`
Example markup using a date field with the variable name `date`:
```
<p>{{format_date fields.date "D" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 16, 2017</p>
```

### Property: `collection`
The following properties and fields are available on the index.html's `collection` property:


#### Property: `id`
This is the collection's id.

Example Markup:
```
<p>{{collection.id}}</p>
```

Example Output:
```
<p>305</p>
```


#### Property: `site_id`
This is the id of the website given by Airship CMS.

Example Markup:
```
<p>{{collection.site_id}}</p>
```

Example Output:
```
<p>62</p>
```


#### Property: `title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.title}}</p>
```

Example Output:
```
<p>Mammals</p>
```


#### Property: `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.name}}</p>
```

Example Output:
```
<p>mammals</p>
```


#### Property: `public_path`
The public path is the identifier for collection following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{collection.public_path}}</p>
```

Example Output:
```
<p>mammals</p>
```


#### Property: `has_public_make`
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


#### Property: `has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

#### Property: `has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

#### Property: `has_comments`
Example Markup:
```
<p>{{collection.has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

#### Property: `has_publish_date`
Example Markup:
```
<p>{{collection.has_publish_date}}</p>
```

Example Output:


#### Property: `show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```


#### Property: `cat_fields`
Example Markup:
Example Output:

#### Property: `layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{collection.layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

#### Property: `priamry_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```


#### Property: `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```


#### Property: `skylines`
Example Markup:
Example Output:


#### Property: `has_plans`
Example Markup:
```
<p>{{collection.has_plans}}</p>
```

Example Output:
```
<p>false</p>
```


## `show.html` template:
- fields and accessible properties.

## `categories.hmtl` template:
- fields and accessible properties.

## `category.html` template:
- fields and accessible properties.
