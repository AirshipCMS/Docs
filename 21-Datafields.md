# Datafields
Content entered in the Admin panel can be rendered using Propellers.

Propellers follow syntax similar to: `{{variable_name}}`.

For fields that contain HTML, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](/documentation/view/datafields#user-content-image), [link](/documentation/view/datafields#user-content-link), or [related aerostats](/documentation/view/datafields#user-content-related-items).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](/documentation/view/datafields#user-content-list-of-images) or [list of links](/documentation/view/datafields#user-content-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

The following examples show how to render the content from each field type:


## Field Type: Text
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `header`:
```
<h1>{{fields.header}}</h1>
```

Example Output:
```
<h1>Airship CMS</h1>
```


## Field Type: Textarea
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `short_description`:
```
<p>{{fields.short_description}}</p>
```

Example Output:
```
<p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
```


## Field Type: Richtext Area
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `description`:
```
<div>{{{fields.description}}}</div>
```

Example Output:
```
<div><p><a href="http://marketing.airshipcms.io" rel="noopener noreferrer" target="_blank">marketing.airshipcms.io</a></p><p><em>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod. Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</em></p></div>
```


## Field Type: Link
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


## Field Type: List of Links
This field is an array of links. The order in which the links are rendered can be controlled either in Admin, or using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller.

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


Example markup using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller:
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


## Field Type: Image
This field allows uploads from either local files, web addresses, or camera. All images are uploaded to Cloudinary.

Aside from the image, there are optional text inputs similar to the [link](/documentation/view/datafields#user-content-link) field, which are title, subtitle, and caption. The url is also accessible, but is not modifiable as it is the url returned from Cloudinary.

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
  <h6>Grumpy Hedgie</h6>
  <p>Lorem ipsum dolor</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/hedgietest_rpaxih.jpg" alt="">
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```


## Field Type: List of Images
This field is an array of images. The order in which the images are rendered can be controlled either in Admin, or using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller.

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
_Note how the outer fields can still be accessed using the `{{../variable_name}}` syntax._
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

Example markup rendering the list of images using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller:
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


## Field Type: Date
This field renders as a unix timestamp by default. To format it, use the [format_date](/documentation/view/propeller-helpers#user-content-format_date) helper.

Example markup using a date field with the variable name `date`:
```
<p>{{format_date fields.date "D" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 16, 2017</p>
```


## Field Type: Checkbox
This field renders `true` if checked, and `false` if not.

The checkbox is useful for adding flags that can be used in combination with propellers, such as [#if](/documentation/view/propeller-helpers#user-content-if-if) or [#unless](/documentation/view/propeller-helpers#user-content-unless), in order to conditionally render content.

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


## Field Type: Number
While this field is a regular text input, it can still be used in place of the [text](/documentation/view/datafields#user-content-text) field to be more semantically correct.

Example markup using a number field with the variable name `population_size`:
```
<p>Population Size: {{fields.population_size}}</p>
```

Example Output:
```
<p>Population Size: 100,000</p>
```


## Field Type: Radio
When using this field, the options must be set upon creation. The options can be edited at any time afterwards, but must be done from the Modify panel in Admin.

Example markup using a radio field with the variable name `is_endangered`:
```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:
```
<p>Endangered: No</p>
```


## Field Type: Select
When using this field, the options must be set upon creation. The options can be edited at any time afterwards, but must be done from the Modify panel in Admin.

Example markup using a select field with the variable name `animal_kingdom`:
```
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:
```
<p>Animal Kingdom: Animals</p>
```

## Field Type: Multiselect
While the multiselect field can be rendered the same way as other `[list]` notated fields, it can also be rendered as a comma separated list for simplicity.

When using this field, the options must be set upon creation. The options can be edited at any time afterwards, but must be done from the Modify panel in Admin.

The order of which the selected items are rendered can be controlled by dragging the options to the proper order while editing the page in Admin.

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

## Field Type: Related Aerostats
This field is not rendered the way the other datafields are. When rendering `{{{help}}}`, this field appears as `related_items`.

Each aerostat is an item from a collection. Items must be published in order to be available for rendering. The content entered in Admin for each item is accessible through the `related_items.related_aerostats_variable_name` field. The order of which the items are rendered can be controlled by either dragging each item into the proper order while editing the page, or by using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller.

Related items attached to a page or item will only render via propellers on the page's template or the item's *show.html* template. Related items will not render on a list index.html or category.html template for a collection. Related items will also not render recursively, for example when an item has related items, and those items have related items.

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

Example markup rendering related aerostats using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller:
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
