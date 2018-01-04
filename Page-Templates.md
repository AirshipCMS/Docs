# Page templates
Page templates render page content. The url for a page is the permalink for the page: `/permalink`.

## Location & Setup
A page template is saved in the `/compartments/templates/` directory. Here is an example of a local project directory with a `root` page:
```
compartments
.
└── templates
    └── root.html
```
## Setting a Page Template in Airship CMS
By default, a layout and template are not automatically set when you create a new page. If you are building a classically rendered website, you will need to set both a [layout](https://airshipcms.io/documentation/view/layouts) and template for the page you are creating.

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

## Renderable Properties
See [Page Properties](https://airshipcms.io/documentation/view/page-properties) for the full list of properties and fields renderable on a page template.

## Excluded Properties
Data from other pages or collections will not render on a page, unless a relationship is created with a "related datafield." Alternatively, if you want to render content that exists outside of the page, you can do an Airship API call and render the content with a script.
