# Schema Setup Guide
This schema setup guide is for someone who has completed the [Quickstart Guide](/documentation/view/quickstart-guide) and is ready to set up their first actual project. 

Before starting, be sure to study how [Pages](/documentation/view/pages), [Collections](/documentation/view/collections), and [Relationships](/documentation/view/relationships) work to form the [Schema & Data Model](/documentation/view/schema-and-data-model) of a project built with Airship.

---

## Draw a Sitemap
Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project. If items from one section should reference another section, map out those relationships as well. If you cannot think of a particular project, you can use this sitemap:

![sitemap](https://user-images.githubusercontent.com/1865400/28704107-27985f58-7304-11e7-9593-db9734f8046e.png)  

## Draw Wireframes
Sketch out a wireframe for each page and collection to show what data will be editable and connected to the CMS.

Example "Homepage" and "News" Collection:

![thumbnails](https://user-images.githubusercontent.com/1865400/28706552-857d5b9e-7310-11e7-814f-dc55014b9c78.png)

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
 
[ SCREENSHOT OF FIELDS ADDED to Homepage to make it match the list ]

Save the page.
 
## Create Additional Pages
Create additional pages and define the fields for those pages.

#### Page Setup
The permalink defines the url for your page. When developing locally, the url will read as `http://localhost:9001/permalink`. When your site is launched, the url will read as `http://subdomain.airshipcms.io/permalink` (_where subdomain is your site subdomain_).

#### Page Rendering
Set the existing `application.html` **layout** for every page. This means all pages in the site will references the same outer "container" markup typically used for the header and footer of the page. You can change this later, though it's easiest to set it to use the default `application.html` layout for now.

Create a new unique **template** for each new page.

#### Page Fields
Define the fields for the page (explain more).

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
