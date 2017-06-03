# Collection `show.html` template:
The following are the avaialbe properties and fields on the show.html template:

## Property: `params`
This property is for pagination.

The following fields are available from the show.html template:
```
page
limit
offset
sort
order
```

For more info about how to use these for pagination, see the documentation on the [create_page_query helper](Propeller-Helpers.md#create_page_query).

Example markup using the `{{create_page_query}}` helper with fields from `params` to create a link with a query string for pagination:
```
<li><a href="/{{aerostat_collection.public_path}}{{create_page_query page='3' sort=params.sort order=params.order limit='15'}}">Mammals (page 3)</a></li>
```

Example Output HTML:
```
<li><a href="/mammals?page=3&amp;limit=15&amp;sort=id&amp;order=asc">Mammals (page 3)</a></li>
```

Example Output Query String:
```
/mammals?page=3&limit=15&sort=id&order=asc
```


## Property: `id`
This is the ID of the item given by Airship CMS.
Example Markup:
```
<p>{{id}}</p>
```

Example Output:
```
<p>3412</p>
```


## Property: `aerostat_collection_id`
This is the ID of the item's collection given by Airship CMS.
Example Markup:
```
<p>{{aerostat_collection_id}}</p>
```

Example Output:
```
<p>305</p>
```


## Property: `permalink`
Example Markup:
```
<p>{{permalink}}</p>
```

Example Output:
```
<p>hedgehog</p>
```


## Property: `sorting_position`
Example Markup:
```
<p>{{sorting_position}}</p>
```

Example Output:
```
<p>0</p>
```


## Property: `published_on`
This is the timestamp of when the current item was published. The publish date can be set in the Admin panel. The timestamp can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date published_on "D" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 23, 2017</p>
```


## Property: `created_at`
This is the timestamp of when the current item was created. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


## Property: `updated_at`
This is the timestamp of when the current item was last updated. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date updated_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


## Property: `fields`
The content endered in the Admin panel for each item is accessible through the item's `fields` property. These fields are similar to [Page fields](Page-Templates.md#page-fields). 

For fields that contain HTML content, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](#field-type-image), [link](#field-type-link), or [related aerostats](#field-type-related-aerostats).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](#field-type-list-of-images) or [list of links](#field-type-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](Propeller-Helpers.md#sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

The following examples show how to render the content from each field type on items:


### Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `name`:
```
<div class="header">
  <h1>{{fields.name}}</h1>
</div>
```

Example Output:
```
<div class="header">
  <h1>Hedgehog</h1>
</div>
```


### Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `short_description`:
```
<p>{{fields.short_description}}</p>
```

Example Output:
```
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
```


### Field Type: `rich text area`
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `description`:
```
<div>{{{fields.description}}}</div>
```

Example Output:
```
<div><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p><p><br></p><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p><p><br></p><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.<br><br></p></div>
```


### Field Type: `image`
Example markup using an image field the variable name `animal_image`:
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
  <h6>Hedgie</h6>
  <p>subtitle for hedgie</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1494993497/media/hedgietest3_dgojvz.jpg" alt="">
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
```


### Field Type: `link`
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
  <a href="http://marketing.airshipcms.io">Resource: Title</a>
  <p>Subtitle</p>
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
```


### Field Type: `number`
Example markup using a number field with the variable name `population_size`:
```
<p>Population Size: {{fields.population_size}}</p>
```

Example Output:
```
<p>Population Size: 100</p>
```


### Field Type: `radio`
Example markup using a radio field with the variable name `is_endangered`:
```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:
```
<p>Endangered: No</p>
```


### Field Type: `select`
Example markup using a select field with the variable name `animal_kingdom`:
```
<p>Selected Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:
```
<p>Selected Animal Kingdom: Animals</p>
```


### Field Type: `multiselect`
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
  <p>5</p>
  <p>2</p>
</div>
```

Example markup rendering the multiselect field as a comma separated list:
```
<p>{{fields.thing}}</p>
```

Example Output:
```
<p>5,2</p>
```


### Field Type: `checkbox`
Example markup using a checkbox with the variable name `show_image`:
```
<div>
  {{#if fields.show_image}}
    {{#each fields.animal_image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image for this animal.</h3>
  {{/if}}
</div>
```

Example Output if Checkbox is Checked:
```
<div>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993497/media/hedgietest3_dgojvz.jpg" alt="">
</div>
```

Exapmle Output if Checkbox is Not Checked:
```
<div>
    <h3>Sorry! No image for this animal.</h3>
</div>
```


### Field Type: `list of images`
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
<div class="sorted-images">
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


### Field Type: `list of links`
Example markup using a list of links with the variable name `additional_resources`:
```
<div class="additional-links">
  {{#each fields.additional_resources}}
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
  {{#sort_list fields.additional_resources sort="title" order="asc"}}
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
    <a href="http://marketing.airshipcms.io">Resource: Other</a>
    <p>other sub</p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: Title</a>
    <p>sub</p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
</div>
```


### Field Type: `related aerostats`
When rendering `{{{help}}}`, this field appears as `related_items`.

Example markup using related aerostats with the variable name `similar_animals`:
```
<div class="similar-animals">
  {{#each related_items.similar_animals}}
  <h4><a href="{{slug}}">{{fields.name}}</a></h4>
  {{/each}}
</div>
```

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/gazelle">Gazelle</a></h4>
  <h4><a href="/mammals/view/guinea-pig">Guinea Pig</a></h4>
  <h4><a href="/mammals/view/grizzly-bear">Grizzly Bear</a></h4>
</div>
```

Example markup rendering related aerostats using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="similar-animals">
  {{#sort_list related_items.similar_animals sort="fields.name" order="asc"}}
  <h4><a href="{{slug}}">{{fields.name}}</a></h4>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/gazelle">Gazelle</a></h4>
  <h4><a href="/mammals/view/grizzly-bear">Grizzly Bear</a></h4>
  <h4><a href="/mammals/view/guinea-pig">Guinea Pig</a></h4>
</div>
```


### Field Type: `date`
Example markup using a date field with the variable name `date`:
```
<p>{{format_date fields.date "D" "us"}}</p>
```

Example Output:
```
<p>Monday, May 01, 2017</p>
```


### Property: `categories`
To use these properties, categories must be enabled in the Admin panel for the collection. The following examples show how to render the available categories properties for each item:


### Property: `id`
This is the ID of the category.

Example Markup:
```
{{#each categories}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>319</p>
```

### Property: `title`
This is the category name.

Example Markup:
```
{{#each categories}}
<p>{{title}}</p>
{{/each}}
```

Example Output:
```
<p>Fluffy</p>
```

### Property: `permalink`
Example Markup:
```
{{#each categories}}
<p>{{permalink}}</p>
{{/each}}
```

Example Output:
```
<p>fluffy</p>
```


### Property: `aerostat_collection_id`
This is the ID of the collection given by Airship CMS.

Example Markup:
```
{{#each categories}}
<p>{{aerostat_collection_id}}</p>
{{/each}}
```

Example Output:
```
<p>305</p>
```

### Property: `created_at`
This is the timestamp of when the category was created.

Example Markup:
```
{{#each categories}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```

### Property: `updated_at`
This is the timestamp of when the category was last updated.

Example Markup:
```
{{#each categories}}
<p>{{format_date updated_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


### Property: `sorting_position`
This is the value of the category's sorting position.

Example Markup:
```
{{#each categories}}
<p>{{sorting_position}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
```


## Property `aerostat_collection`
The following examples show how to render each property from aerostat_collection:

### Property: `id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
<p>{{aerostat_collection.id}}</p>
```

Example Output:
```
<p>305</p>
```


### Property: `site_id`
This is the ID of the website given by Airship CMS.

Example Markup:
```
<p>{{aerostat_collection.site_id}}</p>
```

Example Output:
```
<p>62</p>
```


### Property: `title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.title}}</p>
```

Example Output:
```
<p>Mammals</p>
```


### Property: `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.name}}</p>
```

Example Output:
```
<p>mammals</p>
```


### Property: `public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{aerostat_collection.public_path}}</p>
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
<p>{{aerostat_collection.has_public_make}}</p>
```

Example Output:
```
<p>false</p>
```


### Property: `has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

### Property: `has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

### Property: `has_comments`
Example Markup:
```
<p>{{aerostat_collection.has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

### Property: `has_publish_date`
Example Markup:
```
<p>{{aerostat_collection.has_publish_date}}</p>
```

Example Output:


### Property: `has_products`
Example Markup:
```
<p>{{aerostat_collection.has_products}}</p>
```

Example Output:
```
<p>false</p>
```


### Property: `show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```


### Property: `layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{aerostat_collection.layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

### Property: `primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```


### Property: `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```


### Property: `created_at`
Example Markup:
```
<p>{{format_date created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


### Property: `updated_at`
Exapmle Markup:
```
<p>{{format_date updated_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
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


## Property: `tags`
To use these properties, tags must be enabled in the Admin panel for the collection. The following examples show how to render the available tag properties:

### Property: `id`
This is the ID of the tag given by Airship CMS.

Example Markup:
```
{{#each tags}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>575</p>
```


### Property: `site_id`
This is the ID of the website that the tag belongs to.

Example Markup:
```
{{#each tags}}
<p>{{site_id}}</p>
{{/each}}
```

Example Output:
```
<p>62</p>
```


### Property: `name`
This is the tag name.

Example Markup:
```
{{#each tags}}
<p>{{name}}</p>
{{/each}}
```

Example Output:
```
<p>super-cute</p>
```


### Property: `created_at`
Example Markup:
```
{{#each tags}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```

### Property: `updated_at`
Example Markup:
```
{{#each tags}}
<p>{{format_date updated_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


### Property: `related_items`
Example markup:
```
<div class="similar-animals">
  {{#each related_items.similar_animals}}
  <h4><a href="{{slug}}">{{fields.name}}</a></h4>
  {{#each fields.animal_image}}
  <div class="animal-image">
    <h6>{{title}}</h6>
    <p>{{subtitle}}</p>
    <img src="{{url}}" alt="">
    <p>{{caption}}</p>
  </div>
  {{/each}}
  {{/each}}
</div>
```

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/hedgehog">Hedgehog</a></h4>
  <div class="animal-image">
    <h6>Hedgie Title</h6>
    <p>Subtitle for Hedgie</p>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494993497/media/hedgietest3_dgojvz.jpg" alt="">
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
</div>
```


## Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain.

Example Markup:
```
<p>{{slug}}</p>
```

Example Output:
```
<p>/mammals/view/anteater</p>
```
