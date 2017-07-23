# Collection Templates
Collection Templates include a pre-determined set of the following templates: [`index.html`](/documentation/view/collection-index-template), [`show.html`](/documentation/view/collection-show-template), [`categories.html`](/documentation/view/collection-categories-template), and [`category.html`](/documentation/view/collection-category-template). 

Collection Templates may contain html markup and Collection Propellers markup that renders site content. Templates are not generated with any pre-defined markup in order to give developers the most flexibility when structuring content on a page.

## Collection Templates in your local directory
Whenever you create a collection, the corresponding set of collection templates can be generated in the CMS and downloaded, or manually created in your local project directory.

Using either creation method, the collection template directory is saved in the `/compartments/templates/` directory and the pre-defined templates `index.html`, `show.html`, `categories.html`, and `category.html`, can be used as needed. Here is an example of a local project directory with a `blog` collection:
```
compartments
.
└── templates
    ├── root.html
    └── blog
        ├── categories.html
        ├── category.html
        ├── index.html
        └── show.html
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

## Collection Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On collection templates, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access.

## `index.html` template:
The `index.html` template is used to display all items within a collection.
The public path of the collection, e.g. `/blog`, routes to this page.

Check out the docs for rendering [`index.html`](/documentation/view/collection-index-template), and all available properties and fields that can be accessed from this template.

## `show.html` template:
The `show.html` template renders a single item in a collection.
The url for a post is a collection follows the format: `/collection-public-path/view/item-permalink`.

Check out the docs for rendering [`show.html`](/documentation/view/collection-show-template), and all available properties and fields that can be accessed from this template.


## `categories.html` template:
The `categories.html` template is used as an index for all categories within a collection.
The url for the categories in a collection follows the format: `/collection-public-path/categories`.

Check out the docs for rendering [`categories.html`](/documentation/view/collection-categories-template), and all available properties and fields that can be accessed from this template.

## `category.html` template:
The `category.html` template is used as an index for a sinle category within a collection.
The url for a category in a collection follows the format: `/collection-public-path/categories/category-permalink`.

Check out the docs for rendering [`category.html`](/documentation/view/collection-category-template), and all available properties and fields that can be accessed from this template.
