# Schema Setup Guide
This schema setup guide is for someone who has completed the [Quickstart Guide](https://airshipcms.io/documentation/view/quickstart-guide) and is ready to set up their first actual project. 

Before starting, be sure to study how [Pages](https://airshipcms.io/documentation/view/pages), [Collections](https://airshipcms.io/documentation/view/collections), and [Relationships](https://airshipcms.io/documentation/view/relationships) work to form the [Schema & Data Model](https://airshipcms.io/documentation/view/schema-and-data-model) of a project built with Airship.

---

## Draw a Sitemap
Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project. If items from one section should reference another section, map out those relationships as well. If you cannot think of a particular project, you can use this sitemap:

![sitemap](https://user-images.githubusercontent.com/1865400/28741054-27d16e00-73aa-11e7-8140-1cd2493d9424.jpg)

## Draw Wireframes
Sketch out a wireframe for each page and collection to show what data will be editable and connected to the CMS.

Example "Homepage" and "News" Collection:

![wireframes](https://user-images.githubusercontent.com/1865400/28741053-27b5a33c-73aa-11e7-9bc1-94b9989c2ec4.jpg)

The new "Homepage" will contain the following data:
- **Header Image** (`image`)
- **Header** (`text`)
- **Section 1 Image** (`image`)
- **Section 1 Header** (`text`)
- **Section 1 Description** (`textarea`)
- **Section 2 Image** (`image`)
- **Section 2 Header** (`text`)
- **Section 2 Description** (`textarea`)
- **Section 3 Image** (`image`)
- **Section 3 Header** (`text`)
- **Section 3 Description** (`textarea`)
- **News** (3 posts from "News" collection, `related`)
- **Products** (2 items from "Products collection, `related`)

Each item in the "News" collection will contian the following data:
- **Header Image** (`image`)
- **Header** (`text`)
- **Author** (`text`)
- **Body** (`richtext area`)
- **Short Description** (`textarea`)

For more examples, see some [Use Cases](https://airshipcms.io/use-cases).

## Log in to Airship CMS
Log in to the Airship CMS admin panel `(https://mysite.airshipcms.io/admin)` for your project.  

## Remove Demo Content from Airship CMS
The `root` page (title "Homepage") is the only page you cannot delete in an Airship project. In Airship CMS, click the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> to Modify the page.

Delete all the demo fields. Only the uneditable properties should be left:

![uneditable-fields](https://user-images.githubusercontent.com/1865400/28703393-7f098f50-72ff-11e7-9ac1-ed4cb1cf0d11.png)

Modify the "Homepage" fields to add fields appropriate for your project. This example shows the fields added for the Homepage mocked up above.

![modified_homepage_fields](https://user-images.githubusercontent.com/16835553/28737399-0342c644-738a-11e7-8b96-2b024592eba6.png)

Save the page.
 
## Create Pages
Create additional pages and define the fields for those pages.

### Page Setup
The permalink defines the url for your page. When developing locally, the url will read as `http://localhost:9001/permalink`. When your site is launched, the url will read as `http://mysite.airshipcms.io/permalink` (_where mysite is your site subdomain_).

### Page Rendering
Set the existing `application.html` **layout** for every page. This means all pages in the site will reference the same outer "container" markup typically used for the header and footer of the page. You can change this later, though it's easiest to set it to use the default `application.html` layout for now.

Create a new unique **template** for each new page.

### Page Fields
Define the fields for each page.

These fields will contain all of the data that will be rendered on your site using Airship Propellers. You can create as many fields as needed as long as each `variable name` is unique. By default, the `variable name` is the `title` in lowercase, with spaces converted to underscores. You may customize each variable name, however, keep in mind that having consistency between the title and variable name makes it easier to remember what value to use when rendering data with Propellers.

While the variable name and field type are not editable, you can edit the field `title` by clicking the <img width="27" alt="grey-pencil" src="https://user-images.githubusercontent.com/16835553/28738624-2d7928f8-7390-11e7-9993-61a68b2844ae.png"> at the right of the field. Each field can also be reordered by clicking and dragging the field into the desired position within the list.

Pages that share the same template should have consistent fields in order to use the same Propeller markup.

For more information about each field type, check out the documentation on [Datafields](https://airshipcms.io/documentation/view/datafields).

## Create Collections
Create collections and define the fields for items in those collections.

### Collection Setup
For each collection, add a Title, Public Path, and Name.

The public path defines the url for the collection. When developing locally, the url will read as `http://localhost:9001/public_path`. When your site is launched, the url will read as `http://mysite.airshipcms.io/public_path` (_where mysite is your site subdomain_).

For collections utilizing the `show.html` layout, a single item in the collection will render at `http://mysite.airshipcms.io/public_path/view/permalink`.

For collections utilizing the `categories.html` layout, collection categories will render at `http://mysite.airshipcms.io/public_path/categories`.

For collections utilizing the `category.html` layout, items in a category will render at `http://mysite.airshipcms.io/public_path/categories/category-permalink`.

Example News Collection:
- Title: `News`
- Public Path: `news`

The collection will render at `yourwebsitename.com/news`, categories will render at `yourwebsitename.com/news/categories`, a list of posts within a category will render at `yourwebsitename.com/news/categories/category-permalink`, and a single post will render at `yourwebsitename.com/news/view/permalink`.

### Collection Rendering
Set the existing `application.html` **layout** for every collection.
Create a new unique **template directory** for each new collection.

When you are get familiar with how pages and collections render, you can start to edit your project to more efficiently share layouts and templates accross pages and collections on your site. See [Layouts](https://airshipcms.io/documentation/view/layouts), [Page Templates](https://airshipcms.io/documentation/view/page-templates) and [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more information.

Example News Collection:
- Layout: `application.html`
- Template Directory: `news`

### Collection Fields
Define the fields for an item in the collection.

Example News Collection:

![image](https://user-images.githubusercontent.com/1865400/28741262-25d965e0-73ae-11e7-84b5-aeeff2b239e1.png)

### Primary Label
The only purpose of the `Primary Label` is to identify what field will be set as the "main field" in the list view of items in the CMS.

Example News Collection:
- Set "Header" as the primary label. 

## Set up Relationships
Relationships should be the last thing you set up for your schema. Review the Docs on [Relationships](https://airshipcms.io/documentation/view/relationships) if you haven't done so yet.

To set up a relationship, add a "Related Aerostats" field to the page or collection you want one or more reference posts to appear on.

Example:
In this example, the Homepage pulls some posts from the News Collection. On the **Homepage**, add a Field called "Related News" with type "Related Aerostats" and the collection "News":

![related-news](https://user-images.githubusercontent.com/1865400/28741348-fa676a7c-73af-11e7-81d3-3e82ffcec6d1.jpg)

---

## Add Content
Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

Example:
- Add some content and images to the Homepage.
- Add some posts to the News Collection.
- Go back to the Homepage, and add some posts to the Related News section:

![news-on-homepage](https://user-images.githubusercontent.com/1865400/28741384-c0e70522-73b0-11e7-995c-52aabedb334b.jpg)

---

### Land New Templates
In your terminal, login to your airship site and `airship land` the templates for your new collections and pages. Be sure to git commit or backup your local files _before_ you land. Landing will sync files from the live site to your local development site and overwrite any local files you may have. If you are not using a source control management tool, you can alernatively manually create new templates for your site. See [Page Templates](https://airshipcms.io/documentation/view/page-templates) and [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more on templates.

---

## Start Developing!
Once your pages and collections are set up and demo content is in place, you can start building out your site in your local development environment. See the [Development Guide](https://airshipcms.io/documentation/view/development-guide) for some development guidelines.
