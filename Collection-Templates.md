# Collection Templates
Collection Templates contain html and collection propellers code that renders collection items content. 

Collection Templates include a pre-determined set of the following templates: [`index.html`](https://airshipcms.io/documentation/view/collection-index-template), [`show.html`](https://airshipcms.io/documentation/view/collection-show-template), [`categories.html`](https://airshipcms.io/documentation/view/collection-categories-template), and [`category.html`](https://airshipcms.io/documentation/view/collection-category-template). 

Collection Templates are not generated with any pre-defined markup in order to give developers the most flexibility when structuring content on a page.

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

## Setting a Collection Template Directory in Airship CMS
By default, a layout and template directory are not automatically set when you create a new collection. If you are building a classically rendered website, you will need to set both a [layout](https://airshipcms.io/documentation/view/layouts) and template directory for the collection you are creating.

In Airship CMS, in the `Collection Rendering` section of the collection you are creating or modifying, the `Template Directory` path should be written exactly the way you want it to appear when you reference the collection template files in your local project directory. In this example, the template directory is named `blog`:

![collection-template-dir](https://user-images.githubusercontent.com/1865400/28496728-33406c5a-6f0e-11e7-8b37-96d704d52e75.png)  

### Method 1: Manually Create a Page Template
In your local project directory, create a new directory called `blog` inside the `templates` directory.
```
compartments
.
└── templates
    ├── root.html
    └── blog
```
As needed, create the templates `index.html`, `show.html`, `categories.html`, and `category.html`. You only need to create the templates you need for rendering.
```
compartments
.
└── templates
    ├── root.html
    └── blog
        ├── index.html
        ├── categories.html
        ├── category.html
        └── show.html
```

Add some placeholder text to each template.
```
<h1>Hello! This is the Index!</h1>
```

### Method 2: Downloading a Generated Collection Template Directory
When you set a new `Template Directory` for a collection in Airship CMS, a message will alert you that you can immediately `airship land` the project to download the generated templates that correspond to the template directory set in Airship CMS.

![collection-template-dir-new](https://user-images.githubusercontent.com/1865400/28496727-333ffa5e-6f0e-11e7-89ab-2556e74ac5e2.png)  

When you run `airship land` the templates will download into your local `compartments/templates` directory.
```
compartments
.
└── templates
    ├── root.html
    └── blog
        ├── index.html
        ├── categories.html
        ├── category.html
        └── show.html
```

The generated markup on each template will look something like this:
```
<h1>Aerostat Collection template</h1>
<h2>index.html</h2>

<code>
  <pre>
{{{help}}}
  </pre>
</code>
```

## Viewing the Collection Locally
In Airship CMS, in the `Collection Setup` section of the collection you want to view locally, check that the `Public Path` is written exactly as you want it to appear when someone navigates to your page.

![collection-setup](https://user-images.githubusercontent.com/1865400/28496774-534f94a2-6f0f-11e7-9a13-8128c1d827bf.png)

When you are developing locally, the url of the index will be `localhost:9001/pubic_path`, where `pubic_path` is the value you set for the collection in Airship CMS. In this example, the public_path for the Blog collection was set to `blog` so the full url is `localhost:9001/blog`. When you navigate to this url, you should see the contents of the `index.html` collection template rendered in the browser.

---

## Collection Propellers
"Propellers" is the Airship name for the markup used to render CMS content. Propellers markup follows [HandlebarsJS](http://handlebarsjs.com/) syntax. 

On collection templates, you can add the code `{{{help}}}` within the html markup. This will render a list of all data that is available for rendering. The following sections list the properties and datafields that can be rendered on each template. 

Propellers markup is wrapped by double or triple curly brackets. Properties and Fields typically use double curly brackets like this: `{{variable_name}}` unless the content of the field contains HTML, in which case triple curly brackets should be used: `{{{variable_name}}}`.

Some fields that include a list of content require an `{{#each}}` helper. When rendering `{{{help}}}` on the page, fields that require the `{{#each}}` helper are notated with `[list]` marker next to the field's variable name, followed by a bulleted list of fields to access.

## `index.html` template:
The `index.html` template is used to display all items within a collection.
The public path of the collection, e.g. `/blog`, routes to this page.

Check out the docs for rendering [`index.html`](https://airshipcms.io/documentation/view/collection-index-template), and all available properties and fields that can be accessed from this template.

## `show.html` template:
The `show.html` template renders a single item in a collection.
The url for a post is a collection follows the format: `/collection-public-path/view/item-permalink`.

Check out the docs for rendering [`show.html`](https://airshipcms.io/documentation/view/collection-show-template), and all available properties and fields that can be accessed from this template.

## `categories.html` template:
The `categories.html` template is used as an index for all categories within a collection.
The url for the categories in a collection follows the format: `/collection-public-path/categories`.

Check out the docs for rendering [`categories.html`](https://airshipcms.io/documentation/view/collection-categories-template), and all available properties and fields that can be accessed from this template.

## `category.html` template:
The `category.html` template is used as an index for a sinle category within a collection.
The url for a category in a collection follows the format: `/collection-public-path/categories/category-permalink`.

Check out the docs for rendering [`category.html`](https://airshipcms.io/documentation/view/collection-category-template), and all available properties and fields that can be accessed from this template.
