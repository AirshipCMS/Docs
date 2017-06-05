# Public Make Email Templates
 To use public make email templates, you must create a collection in Admin with public make enabled, and with fields that will hold each item of information you would like submitted.

Example Markup of a public make email template:
```
<h3>You have a new Contact Form Inquiry.</h3>
<p>Submitted: <strong>{{created_at}}</strong></p>
<hr /> 
<h3>Customer Details:</h3>
<p>Name: <strong>{{fields.name}}</strong>
<br>Email: <strong>{{fields.email}}</strong>
<br>Phone: <strong>{{fields.phone}}</strong>
<hr /> 
<h3>Message:</h3>
<p>{{fields.message}}</p>
<hr /> 
<p><em>Please do not reply to this automated email.</em></p>
```

The following examples show how to render different properties and types of data fields:

## Property: `id`
This is the id of the page.

Example Markup:
```
<p>{{id}}</p>
```

Example Output:  
```
<p>182</p>
```


## Property: `published_on`
This is the timestamp of when the current page was published. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>{{format_date published_on "d" "us"}}</p>
```

Example Output:  
```
<p>5/17/2017</p>
```


## Property: `created_at`
This is the timestamp of when the current page was created. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>Submitted: {{format_date created_at "G" "us"}}</p>
```

Example Output:  
```
<p>Submitted: 5/17/2017 2:42:17 AM</p>
```


## Property: `updated_at`
This is the timestamp of when the current page was last updated. It can be formatted using the [format_date](Propeller-Helpers.md#format_date) helper.

Example Markup:
```
<p>Last updated: {{format_date updated_at "U" "us"}}</p>
```

Example Output:  
```
<p>Last updated: Tuesday, May 23, 2017 11:47:04 PM</p>
```


## Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `first_name`:
```
<h1>Name: {{fields.first_name}}</h1>
```

Example Output:
```
<h1>Name: John Doe</h1>
```


## Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `message`:
```
<p>{{fields.message}}</p>
```

Example Output:
```
<p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
```


## Field Type: `rich text area`
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


## Field Type: `image`
Example markup using an image field the variable name `image`:
```
{{#each fields.image}}
<div class="image">
  <h6>{{title}}</h6>
  <p>{{subtitle}}</p>
  <img src="{{url}}" alt="">
  <p>{{caption}}</p>
</div>
{{/each}}
```

Example Output:
```
<div class="image">
  <h6>Client Photo</h6>
  <p>Lorem ipsum dolor</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/client.jpg" alt="">
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```


## Field Type: `link`
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
  <a href="http://marketing.airshipcms.io/">Resource: Info</a>
  <p>Dolor illo in iure voluptas sint?</p>
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```


## Field Type: `number`
Example markup using a number field with the variable name `expected_guest_count`:
```
<p>Expected Guest Count: {{fields.expected_guest_count}}</p>
```

Example Output:
```
<p>Expected Guest Count: 100,000</p>
```


## Field Type: `radio`
Example markup using a radio field with the variable name `event_type`:
```
<p>Type of Event: {{fields.event_type}}</p>
```

Example Output:
```
<p>Type of Event: Wedding</p>
```


## Field Type: `select`
Example markup using a select field with the variable name `venue_type`:
```
<p>Venue Type: {{fields.venue_type}}</p>
```

Example Output:
```
<p>Venue Type: Hotel/Resort</p>
```


## Field Type: `multiselect`
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


## Field Type: `checkbox`
Example markup using a checkbox with the variable name `show_image`:
```
<div>
  {{#if fields.show_image}}
    {{#each fields.image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image available.</h3>
  {{/if}}
</div>
```

Example Output if `show_image` was checked:
```
<div>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/image.jpg" alt="">
</div>
```

Example Output if `show_image` was not checked:
```
<div>
    <h3>Sorry! No image available.</h3>
</div>
```


## Field Type: `list of images`
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
      <h6>Client Image</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/client.jpg" alt="">
      <p>Image subtitle</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
    <div class="image">
      <h6>Other Image</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/other-image.jpg" alt="">
      <p>Image subtitle</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
```

Example markup rendering the list of images using the [#sort_list](Propeller-Helpers.md#sort_list) propeller:
```
<div class="sorted-images">
  {{#sort_list fields.additional_images sort="title" order="asc"}}
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
      <h6>Client Image</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/client.jpg" alt="">
      <p>Image subtitle</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
    <div class="image">
      <h6>Other Image</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/other-image.jpg" alt="">
      <p>Image subtitle</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
``` 


## Field Type: `list of links`
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


## Field Type: `date`
Example markup using a date field with the variable name `date`:
```
<p>{{format_date fields.date "D" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 16, 2017</p>
```
