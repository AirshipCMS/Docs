## Page Templates Location
Your page template should be located in the `/compartments/templates/` directory.

The filename should exactly match what is set as the `Template` name in the Modify section in the admin.

Example project structure with an about and signup page:
```
compartments
.
└── templates
    ├── root.html
    ├── about.html
    └── signup.html
```

---

## Page Properties:
The following properties can be rendered on a Page Template:

### Property: `id`
This is the id of the page.

Example Markup:
```
<p>{{id}}</p>
```

Example Output:  
```
<p>182</p>
```


### Property: `site_id`
This is the id of the site.

Example Markup:
```
<p>{{site_id}}</p>
```

Example Output:  
```
<p>62</p>
```


### Property: `name`
This is the name of the page.

Example Markup:
```
<p>{{name}}</p>
```

Example Output:  
```
<p>About Airship</p>
```


### Property: `permalink`
The permalink is the identifier for page following `/` in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
<p>{{permalink}}</p>
```

Example Output:  
```
<p>about</p>
```


### Property: `layout`
The layout property is the name of the layout, determined in Admin, for the current page. See the [layout docs](Layouts.md) for more information.

Example Markup:
```
<p>{{layout}}</p>
```

Example Output:  
```
<p>application.html</p>
```

### Property: `template`
The template property is the name of the template, determined in Admin, for the current page.

Example Markup:
```
<p>{{template}}</p>
```

Example Output:  
```
<p>animals_and_products.html</p>
```

### Property: `published_on`
This is the timestamp of when the current page was published. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date published_on "d" "us"}}</p>
```

Example Output:  
```
<p>5/17/2017</p>
```


### Property: `created_at`
This is the timestamp of when the current page was created. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date created_at "G" "us"}}</p>
```

Example Output:  
```
<p>5/17/2017 2:42:17 AM</p>
```


### Property: `updated_at`
This is the timestamp of when the current page was last updated. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date updated_at "U" "us"}}</p>
```

Example Output:  
```
<p>Tuesday, May 23, 2017 11:47:04 PM</p>
```


### Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain.

Example Markup:
```
<p>{{slug}}</p>
```

Example Output:  
```
<p>/about</p>
```


## Page Fields:
Content entered in the Admin panel can be rendered using Propellers.

Propellers follow syntax similar to: `{{variable_name}}`.

For fields that contain HTML, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](#field-type-image), [link](#field-type-link), or [related aerostats](#field-type-related-aerostats).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](#field-type-list-of-images) or [list of links](#field-type-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](Propeller-Helpers.md#sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

When using helpers such as `{{#each}}` or `{{#sort_list}}`, the outer properties can still be accessed from within these helpers using the following syntax: `{{../variable_name}}`.

The following examples show how to render the content from each field type on a page:


### Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `header`:
```
<p>{{fields.header}}</p>
```

Example Output:
```
<h1>Cute Animals &amp; Products</h1>
```


### Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `description`:
```
<p>{{fields.description}}</p>
```

Example Output:
```
<p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
```


### Field Type: `rich text area`
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `animal_description`:
```
<div>{{{fields.animal_description}}}</div>
```

Example Output:
```
<div><p><a href="http://marketing.airshipcms.io" rel="noopener noreferrer" target="_blank">marketing.airshipcms.io</a></p><p><em>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod. Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</em></p></div>
```


### Field Type: `image`
Example markup using an image field the variable name `animal_iamge`:
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


### Field Type: `link`
Aside from links, this field is useful for simple text content as it provides more control over how the content is rendered than other text fields.

For example, the link field allows each (optional) `title`, `subtitle`, `url`, and `caption` content to be rendered as separate elements, while the textarea field renders all content within the same HTML element by default.

Example markup using a link field with the variable name `resource_link`:
```
<div class="link">
  {{#each fields.resource_link}}
  <a href="{{url}}">Resource: {{title}}</a>
  <p>{{subtitle}}</p>
  <p>{{caption}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshipcms.io/">Resource: Animal Info</a>
  <p>Dolor illo in iure voluptas sint?</p>
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```


### Field Type: `number`
Example markup using a number field with the variable name `population_size`:
```
<p>Population Size: {{fields.population_size}}</p>
```

Example Output:
```
<p>Population Size: 100,000</p>
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
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:
```
<p>Animal Kingdom: Animals</p>
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


### Field Type: `checkbox`
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


### Field Type: `list of images`
Example markup using a list of images with the variable name `additional_animal_images`:
```
<div class="image-container">
  {{#each fields.additional_animal_images}}
  {{../fields.header}}
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
_Note how the outer fields can still be accessued using the `{{../variable_name}}` syntax._
```
<div class="image-container">
  Cute Animals &amp; Products
    <div class="image">
      <h6>Sleepy Hedgie</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/cute-hedgehogs-311__700_reizde.jpg" alt="">
      <p>img from url</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
  Cute Animals &amp; Products
    <div class="image">
      <h6>Hedgie Dino</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/hedgietest2_a03l7y.jpg" alt="">
      <p>img from file</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
```

Example markup rendering the list of images using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="sorted-images">
  {{#sort_list fields.additional_animal_images sort="title" order="asc"}}
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
      <h6>Hedgie Dino</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/hedgietest2_a03l7y.jpg" alt="">
      <p>img from file</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
    <div class="image">
      <h6>Sleepy Hedgie</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/cute-hedgehogs-311__700_reizde.jpg" alt="">
      <p>img from url</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
``` 


### Field Type: `list of links`
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
    <a href="http://marketing.airshipcms.io/">Resource: link</a>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio</p>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
  </div>
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: other link</a>
    <p>Lorem ipsum dolor rem nam sequi ea</p>
    <p>Lorem ipsum dolor rem nam sequi ea dolor voluptatibus ullam eius. Odit a alias fuga voluptatibus ex ab architecto ipsa? Aut adipisci iusto quia quibusdam rem dicta voluptates, placeat similique quas minima!</p>
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
  <h4><a href="/mammals/view/hedgehog">Hedgehog</a></h4>
  <h4><a href="/mammals/view/bobcat">Bobcat</a></h4>
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
  <h4><a href="/mammals/view/bobcat">Bobcat</a></h4>
  <h4><a href="/mammals/view/hedgehog">Hedgehog</a></h4>
</div>
```


### Field Type: `date`
Example markup using a date field with the variable name `date`:
```
<p>{{format_date fields.date "D" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 16, 2017</p>
```


---

## What cannot be rendered on a page template?
Only page properties render on pages with propellers. Data from other pages or collections will not render with propellers, unless you relate them to the page with a "related datafield."

If you want to render content outside of the page, you need to do an api call and render with a script.
