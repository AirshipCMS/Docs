# Schema Setup Guide
This schema setup guide is for someone who has completed the [Quickstart Guide](/documentation/view/quickstart-guide) and is ready to set up their first actual project. 

Before starting, be sure to study how [Pages](/documentation/view/pages), [Collections](/documentation/view/collections), and [Relationships](/documentation/view/relationships) work to form the [Schema & Data Model](/documentation/view/schema-and-data-model) of a project built with Airship.

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

For more examples, see some [Use Cases](/use-cases) and [Site Map Sketches](/site-map-sketches).

## Log in to Airship CMS
Log in to the Airship CMS admin panel `(https://subdomain.airshipcms.io/admin)` for your project.  

## Remove Demo Content from Airship CMS
The `root` page (title "Homepage") is the only page you cannot delete in an Airship project. In Airship CMS, click the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> to Modify the page.

![demo-page](https://user-images.githubusercontent.com/1865400/28703362-56aa7844-72ff-11e7-910e-b0d69899fa28.png)

Delete all the demo fields. Only the uneditable properties should be left:

![uneditable-fields](https://user-images.githubusercontent.com/1865400/28703393-7f098f50-72ff-11e7-9ac1-ed4cb1cf0d11.png)

Save the page.
Go to Collections and click the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> to Modify the demo "Articles" Collection.

![articles-collection](https://user-images.githubusercontent.com/1865400/28703286-cef5e7ee-72fe-11e7-982e-cf7ad896dc6b.png)

Click "Delete Collection": ![delete-collection](https://user-images.githubusercontent.com/1865400/28703307-ecadaede-72fe-11e7-8985-2ad9a1c881b0.png)

Confirm to delete the collection: ![confirm-delete-collection](https://user-images.githubusercontent.com/1865400/28703311-fd539776-72fe-11e7-8292-dbd588f845f2.png)

## Modify the Homepage
Modify the "Homepage" fields to add fields appropriate for your project:  

![modified_homepage_fields](https://user-images.githubusercontent.com/16835553/28737399-0342c644-738a-11e7-8b96-2b024592eba6.png)

Save the page.
 
## Create Additional Pages
Create additional pages and define the fields for those pages.

#### Page Setup
The permalink defines the url for your page. When developing locally, the url will read as `http://localhost:9001/permalink`. When your site is launched, the url will read as `http://subdomain.airshipcms.io/permalink` (_where subdomain is your site subdomain_).

#### Page Rendering
Set the existing `application.html` **layout** for every page. This means all pages in the site will reference the same outer "container" markup typically used for the header and footer of the page. You can change this later, though it's easiest to set it to use the default `application.html` layout for now.

Create a new unique **template** for each new page.

#### Page Fields
Define the fields for each page.

These fields will contain all of the data that will be rendered on your site using Airship [Propellers](/documentation/view/propeller-helpers). You can create as many fields as needed as long as each `variable name` is unique. By default, the `variable name` is the `title` in lowercase, with spaces converted to underscores. You may customize each variable name, however, keep in mind that having consistency between the title and variable name makes it easier to remember what value to use when rendering data with Propellers.

While the variable name and field type are not editable, you can edit the field `title` by clicking the <img width="27" alt="grey-pencil" src="https://user-images.githubusercontent.com/16835553/28738624-2d7928f8-7390-11e7-9993-61a68b2844ae.png"> at the right of the field. Each field can also be reordered by clicking and dragging the field into the desired position within the list.

Pages that share the same template should have consistent fields in order to use the same Propeller markup.

For more information about each field type, check out the documentation on [Datafields](/documentation/view/datafields).

## Create Collections
Create collections and define the fields for items in those collections.

#### Collection Setup
- collection title (explain more).
- collection name (explain more).
- collection public path (explain more).

#### Collection Rendering
Set the existing `application.html` **layout** for every collection.
Create a new unique **template directory** for each new collection.

When you are get familiar with how pages and collections render, you can start to edit your project to more efficiently share layouts and templates accross pages and collections on your site. See [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates) and [Collection Templates](/documentation/view/collection-templates) for more information.

#### Collection Fields
Define the fields for an item in the collection (explain more).

#### Primary Label
Set a property for the primary label. This is the main label that will display on the list view for items in this collection in the Admin Panel. (explain more).
 
## Set up Relationships
This needs to be done after colletions are setup. (explain more).
Can relate a collection to a page, or a collection to items in a collection. Cannot relate a page to a pge.
Add related datafields to pages and collections in order to set up the framework to create `one-to-many` relationships between pages and collections in your project. If you aren't sure what the relationships are for your project, you can come back to do this later. For more information about relationships, see the [Relationships](/documentation/view/relationships) Docs.

Example:
(talk about the example from the sketches, how posts feed from news and products to homepage). show screenshots of process.

---

## Add Content
Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

---

## Start Developing
Link to Developer Guide.
