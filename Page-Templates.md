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


---

## What cannot be rendered on a page template?
Only page properties render on pages with propellers. Data from other pages or collections will not render with propellers, unless you relate them to the page with a "related datafield."

If you want to render content outside of the page, you need to do an api call and render with a script.
