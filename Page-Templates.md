# Page Templates
Page Templates contain html markup and [Page Propellers](#user-content-page-propellers) markup that renders site content. Templates are not generated with any pre-defined markup in order to give developers the most flexibility when structuring content on a page.

## Page Templates in your local directory
Whenever you create a page, the corresponding page template can be generated in the CMS and downloaded, or manually created in your local project directory.

Using either creation method, the page template is saved in the `/compartments/templates/` directory. Here is an example of a local project directory with a `root` page:
```
compartments
.
└── templates
    └── root.html
```

---

## Setting a Page Template in Airship CMS
By default, a layout and template are not automatically set when you create a new page. If you are building a classically rendered website, you will need to set both a [layout](/documentation/view/layouts) and template for the page you are creating.

In Airship CMS, in the `Page Rendering` section of the page you are creating or modifying, the `Template` filename should be written exactly the way you want it to appear when you reference the file in your local project directory. In this example, the template is named `about.html`:

![page-template-about](https://user-images.githubusercontent.com/1865400/28495841-061792e2-6ef7-11e7-8882-a38d050eace5.png)  

### Method 1: Manually Create a Page Template
In your local project directory, create a new html file called `about.html` and save it into the `templates` directory.
```
compartments
.
└── templates
    ├── root.html
    └── about.html
```

Add some placeholder text to the blank `about.html` template:
```
<h1>Hello!</h1>
```

### Method 2: Downloading a Generated Page Template
When you set a new `Template` for a page in Airship CMS, a message will alert you that you can immediately `airship land` the project to download the generated template file that corresponds to the template set in Airship CMS.

![page-template-about-new](https://user-images.githubusercontent.com/1865400/28495840-0616a706-6ef7-11e7-8ffc-c344fdd8b6ee.png)

When you run `airship land` the file will download into your local `compartments/templates` directory.
```
compartments
.
└── templates
    ├── root.html
    └── about.html
```

The generated markup on the page will look something like this:
```
<p>about Template</p>
{{{ help }}}
```

## Viewing the Page Locally
In Airship CMS, in the `Page Setup` section of the page you want to view locally, check that the `Permalink` is written exactly as you want it to appear when someone navigates to your page.

![page-setup](https://user-images.githubusercontent.com/1865400/28495696-2ddafaa2-6ef3-11e7-989d-fdd5a644800a.png)  

When you are developing locally, the url of the page will be `localhost:9001/permalink`, where `permalink` is the value you set for the page in Airship CMS. In this example, the permalink for the About page was set to `about` so the full url is `localhost:9001/about`. When you navigate to this url, you should see the contents of the `about.html` template rendered in the browser.

---

## Page Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On any page, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the [Page Properties](#user-content-page-properties) and [Page Datafields](#user-content-page-datafields) that can be rendered on a page. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access.

## Page Properties:
The following properties can be rendered on a page template:
- `id`
- `site_id`
- `name`
- `permalink`
- `layout`
- `template`
- `published_on`
- `created_at`
- `updated_at`
- `slug`
- `related_items [list]`

The following field types can be rendered on a page template:
- `text`
- `textarea`
- `richtext area`
- `image`
- `link`
- `number`
- `radio`
- `select`
- `multiselect`
- `checkbox`
- `list of images`
- `list of links`
- `date`

To see examples of how each property and field renders, see [Page Properties](/documentation/view/page-properties).

---

## Properties you can't access from a page template
Data from other pages or collections will not render with Airship Propellers, unless a relationship is created with a "related datafield." Alternatively, if you want to render content that exists outside of the page, you can do an Airship API call and render the content with a script.
