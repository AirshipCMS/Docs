# Page Templates
Your page template should be located in...
The filename should match what is set in the Modify section in the admin...

---

## Page Properties:
The following properties can be rendered on a Page Template:


### Property: `name`
This is the name of the page. Example Markup:
```
<p>{{name}}</p>
```
Example Output:  
**About Airship**  


### Property: `permalink`
The permalink is the identifier for page following `/` in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. Example Markup:
```
<p>{{permalink}}</a>
```

Example Output:  
**about**


### Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain. Example Markup:
```
<p>{{slug}}</a>
```

Example Output:  
**/about**


## Page Fields:
Content entered in the Admin panel can be rendered using Propellers.

Propellers follow syntax similar to: `{{variable_name}}`.

For fields that contain HTML, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields will be noted with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](#field-type-image), [link](#field-type-link), or [related aerostats](#field-type-related-aerostats).

The following examples show how to render the content from each field type on a page:


### Field Type: `text`
The text field is a simple text input. It's useful for content with small amount of phrasing, such as headers or titles.

Example markup using a text field with the variable name `header`:
```
<p>{{fields.header}}</p>
```

Example Output:

**Airship CMS**


### Field Type: `textarea`
The textarea field is useful for plain multiline content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `description`:
```
<p>{{fields.description}}</p>
```

Example Output:

**Lorem ipsum dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.**


### Field Type: `rich text area`
The rich text area, or WYSIWYG editor, is useful for custom formatting or adding various content other than text such as images, links, or lists.

This field requires an extra set of `{}`, similar to rendering fields that contain HTML elements.

Example markup using a rich text area with the variable name `animal_description`:
```
<div>{{{fields.animal_description}}}</div>
```

Example Output:

- List Item 1
- List Item 2

**Lorem ipsum dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. *Id iusto enim repellat veniam sed totam quod. Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at?* Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.**


### Field Type: `image`
Example markup using an image field the variable name `animal_iamge`:
Example Output:


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

[Resource: Animal Info](http://https://www.google.com/search?q=cute+hedgehogs&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjh4bqx9PzTAhXDy1QKHWg4BV0Q_AUIBigB&biw=1778&bih=887)

**Lorem ipsum dolor illo in iure voluptas sint?**

**Lorem ipsum dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.**


### Field Type: `number`
Example markup using a number field with the variable name `population_size`:
```
<p>Population Size: {{fields.population_size}}</p>
```

Example Output:

**Population Size: 100,000**


### Field Type: `radio`
Example markup using a radio field with the variable name `is_endangered`:
```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:

**Endangered: No**


### Field Type: `select`
Example markup using a select field with the variable name `animal_kingdom`:
```
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:

**Animal Kingdom: Animals**


### Field Type: `multiselect`
Example markup using a multiselect field with the variable name `things`:
```
<p>{{fields.thing}}</p>
```

Example Output:

**Thing 1, Thing 2**


### Field Type: `checkbox`
Example markup using a with the variable name ``:
Example Output:


### Field Type: `list of images`
Example markup using a with the variable name ``:
Example Output:


### Field Type: `list of links`
Example markup using a with the variable name `things`:
Example Output:


### Field Type: `related aerostats`
Example markup using a with the variable name ``:
Example Output:


### Field Type: `date`
Example markup using a with the variable name ``:
Example Output:


---

## What cannot be rendered on a page template?
Only page properties render on pages with propellers. Data from other pages or collections will not render with propellers, unless you relate them to the page with a "related datafield."

If you want to render content outside of the page, you need to do an api call and render with a script.
