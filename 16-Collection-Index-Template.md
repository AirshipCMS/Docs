# Collection `index.html` template:
The following properties and fields can be rendered on the index.html template:

## Property: `params`

## Property: `items`

### Property: `id`

### Property: `aerostat_collection_id`

### Property: `permalink`

### Property: `sorting_position`

### Property: `published_on`

### Property: `created_at`
This is the timestamp of when the current item was created. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
{{#each items}}
<p>{{format_date created_at "o" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-17T07:01:45.9940000+00:00</p>
<p>2017-05-17T06:47:16.2810000+00:00</p>
```


### Property: `updated_at`
This is the timestamp of when the current item was last updated. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
{{#each items}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-30 06:22:59Z</p>
```

### Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain.

Example Markup:
```
{{#each items}}
<p>{{slug}}</p>
{{/each}}
```

Example Output:
```
<p>/mammals/view/anteater</p>
<p>/mammals/view/bobcat</p>
```

### Items `fields`
The content endered in the Admin panel for each item is accessible through the item's `fields` property. These fields are similar to [Page fields](Page-Templates.md#page-fields), though the related_items field for each item is not available within the collection index.html. 

For fields that contain HTML content, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](#field-type-image), [link](#field-type-link), or [related aerostats](#field-type-related-aerostats).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](#field-type-list-of-images) or [list of links](#field-type-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](Propeller-Helpers.md#sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

The following examples show how to render the content from each field type on items:


#### Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `name`:
```
{{#each items}}
<div class="header">
  <h1>{{fields.name}}</h1>
</div>
{{/each}}
```

Example Output:
```
<div class="header">
  <h1>Anteater</h1>
</div>
<div class="header">
  <h1>Bobcat</h1>
</div>
```


#### Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `short_description`:
```
{{#each items}}
<div>
  <p>{{fields.short_description}}</p>
</div>
{{/each}}
```

Example Output:
```
<div>
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
<div>
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
```


#### Field Type: `rich text area`
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `description`:
```
{{#each items}}
<div>
  <p>{{{fields.description}}}</p>
</div>
{{/each}}
```

Example Output:
```
<div>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p><p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.<br>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
<div>
  <p>&lt;p&gt;Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.&lt;/p&gt;&lt;p&gt;Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.&lt;br&gt;Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.&lt;br&gt;Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.&lt;br&gt;&lt;br&gt;&lt;/p&gt;</p>
</div>
```


#### Field Type: `image`
Example markup using an image field the variable name `animal_image`:
```
{{#each items}}{{#each fields.animal_image}}
<div class="animal-image">
  <h6>{{title}}</h6>
  <p>{{subtitle}}</p>
  <img src="{{url}}" alt="">
  <p>{{caption}}</p>
</div>
{{/each}}{{/each}}
```

Example Output:
```
<div class="animal-image">
  <h6>Woof</h6>
  <p>Subtitle</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1495003948/media/Dingo-Pup2_c158dn.jpg" alt="">
  <p></p>
</div>
<div class="animal-image">
  <h6>Puppy</h6>
  <p></p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1495004310/media/1d95c504bf7dda96a76bfa638f711779_qjvlav.jpg" alt="">
  <p></p>
</div>
```


#### Field Type: `link`
Aside from links, this field is useful for simple text content as it provides more control over how the content is rendered than other text fields.

For example, the link field allows each (optional) `title`, `subtitle`, `url`, and `caption` content to be rendered as separate elements, while the textarea field renders all content within the same HTML element by default.

Example markup using a link field with the variable name `resource_link`:
```
{{#each items}}{{#each fields.resource}}
<div class="link">
  <a href="{{url}}">Resource: {{title}}</a>
  <p>{{subtitle}}</p>
  <p>{{caption}}</p>
</div>
{{/each}}{{/each}}
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshipcms.io">Resource: Title</a>
  <p>subtitle</p>
  <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
</div>
<div class="link">
  <a href="http://marketing.airshipcms.io">Resource: Title &amp; Url</a>
  <p></p>
  <p></p>
</div>
```


#### Field Type: `number`
Example markup using a number field with the variable name `population_size`:
```
{{#each items}}
<p>Population Size: {{fields.population_size}}</p>
{{/each}}
```

Example Output:
```
<p>Population Size: 100,000</p>
<p>Population Size: 90,000</p>
```


#### Field Type: `radio`
Example markup using a radio field with the variable name `is_endangered`:
```
{{#each items}}
<p>Endangered: {{fields.is_endangered}}</p>
{{/each}}
```

Example Output:
```
<p>Endangered: No</p>
<p>Endangered: No</p>
```


#### Field Type: `select`
Example markup using a select field with the variable name `animal_kingdom`:
```
{{#each items}}
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
{{/each}}
```

Example Output:
```
<p>Animal Kingdom: Animals</p>
<p>Animal Kingdom: Animals</p>
```


#### Field Type: `multiselect`
While the multiselect field can be rendered the same way as other `[list]` notated fields, it can also be rendered as a comma separated list for simplicity.

Example markup using a multiselect field with the variable name `things`:
```
{{#each items}}
<div class="all-the-things">
  {{#each fields.thing}}
  <p>{{this}}</p>
  {{/each}}
</div>
{{/each}}
```

Example Output:
```
<div class="all-the-things">
  <p>1</p>
  <p>2</p>
</div>
<div class="all-the-things">
  <p>1</p>
  <p>2</p>
  <p>3</p>
  <p>4</p>
  <p>5</p>
</div>
```

Example markup rendering the multiselect field as a comma separated list:
```
{{#each items}}
<p>{{fields.thing}}</p>
{{/each}}
```

Example Output:
```
<p>1,2</p>
<p>1,2,3,4,5</p>
```


#### Field Type: `checkbox`
Example markup using a checkbox with the variable name `show_image`:
```
{{#each items}}
<div>
  {{#if fields.show_image}}
    {{#each fields.animal_image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image for this animal.</h3>
  {{/if}}
</div>
{{/each}}
```

Example Output:
```
<div>
    <h3>Sorry! No image for this animal.</h3>
</div>
<div>
      <img src="http://res.cloudinary.com/airship/image/upload/v1495003519/media/ef774a4d8d73657ddf2bcdb48769014b_n8x9t2.jpg" alt="">
</div>
```


#### Field Type: `list of images`
Example markup using a list of images with the variable name `additional_images`:
```
{{#each items}}
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
{{/each}}
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
<div class="image-container">
    <div class="image">
      <h6></h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494994000/media/cute-baby-jaguar-wallpaper-3_ijwwci.jpg" alt="">
      <p></p>
      <p></p>
    </div>
    <div class="image">
      <h6>Other kitty</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494994017/media/A-ferocious-jaguar-cub_ronnu1.jpg" alt="">
      <p></p>
      <p></p>
    </div>
</div>
```

Example markup rendering the list of images using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
{{#each items}}
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
{{/each}}
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
<div class="sorted-images">
    <div class="image">
      <h6></h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494994000/media/cute-baby-jaguar-wallpaper-3_ijwwci.jpg" alt="">
      <p></p>
      <p></p>
    </div>
    <div class="image">
      <h6>Other kitty</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494994017/media/A-ferocious-jaguar-cub_ronnu1.jpg" alt="">
      <p></p>
      <p></p>
    </div>
</div>
``` 


#### Field Type: `list of links`
Example markup using a list of links with the variable name `additional_resources`:
```
{{#each items}}
<div class="additional-links">
  {{#each fields.additional_resources}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
  </div>
  {{/each}}
</div>
{{/each}}
```

Example Output:
```
<div class="additional-links">
  <div class="link">
    <a href="">Resource: Resource</a>
    <p></p>
    <p></p>
  </div>
  <div class="link">
    <a href="">Resource: Resource</a>
    <p></p>
    <p></p>
  </div>
  <div class="link">
    <a href="">Resource: Resource</a>
    <p></p>
    <p></p>
  </div>
</div>
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis.</a>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis?</p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
  <div class="link">
    <a href="">Resource: </a>
    <p></p>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam. Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
  </div>
</div>
```

Example markup rendering the list of links using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
{{#each items}}
<div class="additional-links">
  {{#sort_list fields.additional_resources sort="title" order="desc"}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
  </div>
  {{/sort_list}}
</div>
{{/each}}
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
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: title</a>
    <p>Lorem ad voluptatibus amet fugit excepturi facilis?</p>
    <p></p>
  </div>
  <div class="link">
    <a href="">Resource: Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis.</a>
    <p>subtitle</p>
    <p></p>
  </div>
</div>
```


#### Field Type: `date`
Example markup using a date field with the variable name `date`:
```
{{#each items}}
<p>{{format_date fields.date "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Tuesday, May 23, 2017</p>
<p>Wednesday, May 10, 2017</p>
```

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