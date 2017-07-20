## Location of Templates
Your page template should be located in the `/compartments/templates/` directory. The filename of the template should exactly match what is set as the `template` name in the Modify section for the page in Airship CMS. If you set the template in Airship CMS, you can immediately `airship land` the project to generate a template file with the proper name. Here is an example of a project with `about` and `signup` pages:
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

### `id`

### `site_id`

### `name`

### `permalink`

### `layout`

### `template`

### `published_on`

### `created_at`

### `updated_at`

### `slug`

---

## Page Fields:
Content entered in Airship CMS Admin Panel can be rendered on a page template using propellers markup. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

Propellers markup is wrapped by double or triple curly brackets. Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content requires an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access.

The following examples show how to render the content from each field type on a page:

### `text`

### `textarea`

### `richtext area`

### `image`

### `link`

### `number`

### `radio`

### `select`

### `multiselect`

### `checkbox`

### `list of images`

### `list of links`

### `related aerostats`

### `date`

---

## Properties you can't access from a page template
Only page properties render on pages with propellers. Data from other pages or collections will not render with propellers, unless you relate them to the page with a "related datafield."

If you want to render content outside of the page, you need to do an api call and render with a script.
