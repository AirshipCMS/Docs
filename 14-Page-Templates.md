## Page Templates
Whenever you create a page, the corresponding page template can be generated in the CMS and downloaded, or manually created in your local project directory.

Using either creation method, the page template needs to end up in the `/compartments/templates/` directory. Here is an example of a local project directory with a `root` page:
```
compartments
└── templates
    └──  root.html
```

## Setting a Page Template in Airship CMS
By default, a layout and template are not automatically set when you create a new page. If you are building a classically rendered website, you will need to set both a [layout](/documentation/view/layouts) and page template for the page you are creating.

In the `Page Rendering` section of the page you are creating or modifying, the template filename should be written exactly the way you want it to appear when you reference the file in your local project directory. In this example, the template is named `about.html`:

![page-rendering-680x223](https://user-images.githubusercontent.com/1865400/28495584-5cccb5ea-6eed-11e7-99ff-ba2b5a227e8b.png)

### Method 1: Manually Create a Page Template
In your local project directory, create a new html file called `about.html` and save it into the `templates` directory.
```
compartments
└── templates
    ├── root.html
    └──  about.html
```
Add some placeholder text to the blank `about.html` template:
```
<h1>Hello!</h1>
```
When you navigate to the page in your browser, you should see the contents of the bew `about.html` template rendered on the page.

[ screenshot of browser ]  

### Method 2: Downloading a Generated Page Template
If you set the template in Airship CMS, you can immediately `airship land` the project to generate a template file with the proper name. 

---

## Page Properties:
The following properties can be rendered on a page template:

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
