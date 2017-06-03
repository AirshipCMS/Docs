# Product Collection `show.html` Template:
The following properties and fields can be rendered on the show.html template:

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
<li><a href="/{{aerostat_collection.public_path}}{{create_page_query page='1' sort=params.sort order=params.order limit='15'}}">Supplies (page 1)</a></li>
```

Example Output HTML:
```
<li><a href="/supplies?page=1&amp;limit=15&amp;sort=id&amp;order=asc">Supplies (page 1)</a></li>
```

Example Output Query String:
```
/supplies?page=1&limit=15&sort=id&order=asc
```


## Property: `id`
This is the ID of the item given by Airship CMS.
Example Markup:
```
<p>{{id}}</p>
```

Example Output:
```
<p>3471</p>
```


## Property: `aerostat_collection_id`
This is the ID of the item's collection given by Airship CMS.
Example Markup:
```
<p>{{aerostat_collection_id}}</p>
```

Example Output:
```
<p>307</p>
```


## Property: `permalink`
The permalink is the identifier for the item following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
<p>{{permalink}}</p>
```

Example Output:
```
<p>food</p>
```


## Property: `product_title`
This is the identifier or name of the item.

Example Markup:
```
<p>{{product_title}}</p>
```

Example Output:
```
<p>Food</p>
```


## Property: `sorting_position`
This is the sort order value of the item.

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
<p>{{format_date published_on "f" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 23, 2017 12:00 AM</p>
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
<p>{{format_date updated_at "u" "us"}}</p>
```

Example Output:
```
<p>2017-06-01 04:29:37Z</p>
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
{{#each items}}
<div class="header">
  <h1>{{fields.name}}</h1>
</div>
{{/each}}
```

Example Output:
```
<div class="header">
  <h1>Toy</h1>
</div>
<div class="header">
  <h1>Food</h1>
</div>
```


### Field Type: `textarea`
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


### Field Type: `rich text area`
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


### Field Type: `image`
Example markup using an image field the variable name `product_image`:
```
{{#each items}}{{#each fields.product_image}}
<div class="product-image">
  <h6>{{title}}</h6>
  <p>{{subtitle}}</p>
  <img src="{{url}}" alt="">
  <p>{{caption}}</p>
</div>
{{/each}}{{/each}}
```

Example Output:
```
<div class="product-image">
  <h6>Title</h6>
  <p>Subtitle</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1495003948/media/dog-toy.jpg" alt="">
  <p></p>
</div>
<div class="product-image">
  <h6>Other Title</h6>
  <p></p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1495004310/media/1d95c504bf7dda96a76bfa638f711779_qjvlav.jpg" alt="">
  <p></p>
</div>
```


### Field Type: `link`
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


### Field Type: `number`
Example markup using a number field with the variable name `recommendations`:
```
{{#each items}}
<p>Recommendations: {{fields.recommendations}}</p>
{{/each}}
```

Example Output:
```
<p>Recommendations: 100,000</p>
<p>Recommendations: 90,000</p>
```


### Field Type: `radio`
Example markup using a radio field with the variable name `is_seasonal`:
```
{{#each items}}
<p>Seasonal: {{fields.is_seasonal}}</p>
{{/each}}
```

Example Output:
```
<p>Seasonal: No</p>
<p>Seasonal: No</p>
```


### Field Type: `select`
Example markup using a select field with the variable name `for_pet_types`:
```
{{#each items}}
<p>For Pet Types: {{fields.for_pet_types}}</p>
{{/each}}
```

Example Output:
```
<p>For Pet Types: Dogs</p>
<p>For Pet Types: Cats</p>
```


### Field Type: `multiselect`
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


### Field Type: `checkbox`
Example markup using a checkbox with the variable name `show_image`:
```
{{#each items}}
<div>
  {{#if fields.show_image}}
    {{#each fields.product_image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image for this product.</h3>
  {{/if}}
</div>
{{/each}}
```

Example Output:
```
<div>
    <h3>Sorry! No image for this product.</h3>
</div>
<div>
      <img src="http://res.cloudinary.com/airship/image/upload/v1495003519/media/ef774a4d8d73657ddf2bcdb48769014b_n8x9t2.jpg" alt="">
</div>
```


### Field Type: `list of images`
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
      <h6>Image Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p>Image Subtitle</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
    <div class="image">
      <h6>Other Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p>Other Subtitle</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
</div>
<div class="image-container">
    <div class="image">
      <h6></h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p></p>
      <p></p>
    </div>
    <div class="image">
      <h6>Other Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
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
      <h6>Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p>Subtitle</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
    <div class="image">
      <h6>Other Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p>Other Subtitle</p>
      <p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
    </div>
</div>
<div class="sorted-images">
    <div class="image">
      <h6>Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p></p>
      <p></p>
    </div>
    <div class="image">
      <h6>Other Title</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494993551/media/some_image.jpg" alt="">
      <p></p>
      <p></p>
    </div>
</div>
``` 


### Field Type: `list of links`
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


### Field Type: `related aerostats`
When rendering `{{{help}}}`, this field appears as `related_items`.

Example markup using related aerostats with the variable name `related_products`:
```
<div class="similar-products">
  {{#each related_items.related_products}}
  <h4><a href="{{slug}}">{{product_title}}</a></h4>
  {{/each}}
</div>
```

Example Output:
```
<div class="similar-products">
  <h4><a href="/supplies/view/toy">Toy</a></h4>
</div>
```

Example markup rendering related aerostats using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="similar-products">
  {{#sort_list related_items.related_products sort="product_title" order="asc"}}
  <h4><a href="{{slug}}">{{product_title}}</a></h4>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="similar-products">
  <h4><a href="/supplies/view/food">Food</a></h4>
  <h4><a href="/supplies/view/toy">Toy</a></h4>
</div>
```


### Field Type: `date`
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


## Property: `categories`
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
<p>321</p>
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
<p>Essentials</p>
```

### Property: `permalink`
The permalink is the identifier for the category following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
{{#each categories}}
<p>{{permalink}}</p>
{{/each}}
```

Example Output:
```
<p>essentials</p>
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
<p>307</p>
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
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-06-01 04:43:46Z</p>
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

#### Property: `id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
<p>{{aerostat_collection.id}}</p>
```

Example Output:
```
<p>307</p>
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
<p>Supplies</p>
```


### Property: `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.name}}</p>
```

Example Output:
```
<p>supplies</p>
```


### Property: `public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{aerostat_collection.public_path}}</p>
```

Example Output:
```
<p>supplies</p>
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
This shows whether or not the collection contains any products.

Example Markup:
```
<p>{{aerostat_collection.has_products}}</p>
```

Example Output:
```
<p>true</p>
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
<p>supplies.html</p>
```

### Property: `primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.primary_label}}</p>
```

Example Output:
```
<p>Product Title</p>
```


### Property: `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.template_directory}}</p>
```

Example Output:
```
<p>supplies</p>
```


### Property: `created_at`
This is the timestamp for when the collection was created.

Example Markup:
```
<p>{{format_date collection.created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


### Property: `updated_at`
This is the timestamp for when the collection was last updated.

Example Markup:
```
<p>{{format_date collection.updated_at "u" "us"}}</p>
```

Example Output:
```
<p>2017-06-01 04:29:27Z</p>
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
<p>583</p>
<p>584</p>
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
<p>Dog</p>
<p>Cat</p>
```


### Property: `created_at`
This is the timestamp for when the tag was created.

Example Markup:
```
{{#each tags}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
<p>Wednesday, May 17, 2017</p>
```


### Property: `updated_at`
This is the timestamp of when the tag was last updated.

Example Markup:
```
{{#each tags}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-17 08:03:28Z</p>
<p>2017-05-17 08:03:28Z</p>
```


## Property: `product_variations`
Product variations are for distinguishing variations between products that are the same except for differences such as sizes or colors.

### Property: `id`
This is the ID of the variation given by Airship CMS.

Example Markup:
```
{{#each product_variations}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>1954</p>
<p>1955</p>
```


### Property: `aerostat_id`
This is the ID of the variations root product given by Airship CMS.

Example Markup:
```
{{#each product_variations}}
<p>{{aerostat_id}}</p>
{{/each}}
```

Example Output:
```
<p>3471</p>
<p>3471</p>
```


### Property: `product_variation_title`
This is the identifier or name of the variation.

Example Markup:
```
{{#each product_variations}}
<p>{{product_variation_title}}</p>
{{/each}}
```

Example Output:
```
<p>Cat Food</p>
<p>Dog Food</p>
```


### Property: `product_variation_image`
Example Markup:
```
{{#each product_variations}}
{{/each}}
```

Example Output:


### Property: `product_variation_description`
This is a short text description of the variation.

Example Markup:
```
{{#each product_variations}}
<p>{{product_variation_description}}</p>
{{/each}}
```

Example Output:
```
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
```


### Property: `price`
The following examples show how to render the properties on price:

#### Property: `usd`
The `{{format_currency}}` helper is useful for fields that contain currency values. For more information, see the [format_currency](Propeller-Helpers.md#format_currency) documentation.

Example Markup:
```
{{#each product_variations}}
<p>{{format_currency price.usd "usd"}}</p>
{{/each}}
```

Example Output:


### Property: `sale_price`
The `{{format_currency}}` helper is useful for fields that contain currency values. For more information, see the [format_currency](Propeller-Helpers.md#format_currency) documentation.

#### Property: `usd`
Example Markup:
```
{{#each product_variations}}
<p>{{format_currency sale_price.usd "usd" 2}}</p>
{{/each}}
```

Example Output:


### Property: `weight`
This is the weight of the variation in pounds and/or ounces.

Example Markup:
```
{{#each product_variations}}
<p>{{weight}}</p>
{{/each}}
```

Example Output:


### Property: `in_stock`
This shows whether or not the product variation is in stock.

Example Markup:
```
{{#each product_variations}}
<p>{{in_stock}}</p>
{{/each}}
```

Example Output:
```
<p>false</p>
<p>true</p>
```


### Property: `inventory`
This is the available amount of the product.

Example Markup:
```
{{#each product_variations}}
<p>{{inventory}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
<p>5</p>
```


### Property: `sorting_position`
This is the sort order value of the product.

Example Markup:
```
{{#each product_variations}}
<p>{{sorting_position}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
<p>1</p>
```


### Property: `published_on`
This is the timestamp of when the variation was published.

Example Markup:
```
{{#each product_variations}}
<p>{{format_date published_on "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 30, 2017</p>
<p>Wednesday, May 29, 2017</p>
```


### Property: `on_sale`
This shows whether or not the variation is on sale for a discounted price.

Example Markup:
```
{{#each product_variations}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>false</p>
<p>true</p>
```


### Property: `created_at`
This is the timestamp for when the product variation was created.

Example Markup:
```
{{#each product_variations}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
<p>Wednesday, May 17, 2017</p>
```


### Property: `updated_at`
This is the timestamp for when the product variation was last updated.

Example Markup:
```
{{#each product_variations}}
<p>{{format_date updated_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Thursday, June 01, 2017</p>
<p>Thursday, June 01, 2017</p>
```


### Property: `related_items`
This property holds information from the related aerostats field type.

For more information, see the section on [related aerostat](#field-type-related-aerostats) field types.
