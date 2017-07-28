# Schema Setup Guide
This schema setup guide is for someone who has completed the [Quickstart Guide](/documentation/view/quickstart-guide) and is ready to set up their first actual project. 

Before starting, be sure to study how [Pages](/documentation/view/pages), [Collections](/documentation/view/collections), and [Relationships](/documentation/view/relationships) work to form the [Schema & Data Model](/documentation/view/schema-and-data-model) of a project built with Airship.

---

## Draw a Sitemap Sketch
Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project. If items from one section should reference another section, map out those relationships as well.

[ EXAMPLE SKETCH ]

For more examples, see some [Use Cases](/use-cases) and [Site Map Sketches](/site-map-sketches)

## Log in to Airship CMS
Log in to the Airship CMS admin panel `(https://subdomain.airshipcms.io/admin)` for your project.  

## Remove Demo Content from Airship CMS
- The `root` page (title "Homepage") is the only page you cannot delete in an Airship project. In Airship CMS, click the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> to Modify the page.

![demo-page](https://user-images.githubusercontent.com/1865400/28703362-56aa7844-72ff-11e7-910e-b0d69899fa28.png)

- Delete all the demo fields. Only the uneditable properties should be left:

![uneditable-fields](https://user-images.githubusercontent.com/1865400/28703393-7f098f50-72ff-11e7-9ac1-ed4cb1cf0d11.png)

- Save the page.
- Go to Collections and click the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> to Modify the demo "Articles" Collection.

![articles-collection](https://user-images.githubusercontent.com/1865400/28703286-cef5e7ee-72fe-11e7-982e-cf7ad896dc6b.png)

- Click "Delete Collection": ![delete-collection](https://user-images.githubusercontent.com/1865400/28703307-ecadaede-72fe-11e7-8985-2ad9a1c881b0.png)

- Confirm to delete the collection: ![confirm-delete-collection](https://user-images.githubusercontent.com/1865400/28703311-fd539776-72fe-11e7-8292-dbd588f845f2.png)

## Set up Pages
 - Modify the "Homepage" fields to change what shows for the root page of your site.
 - Create additional [Pages](/documentation/view/pages) and [Collections](/documentation/view/collections) for your project and define the dynamic datafields needed for each Page and Collection. 
 
 When you set up the rendering section for pages and collections:  
 - Set the existing `application.html` **layout** for every page and collection.  
 - Create a new unique **template** for each page.  
 - Create a new unique **template directory** for each collection.  
When you are get familiar with how pages and collections render, you can start to edit your project to more efficiently share layouts and templates accross pages and collections on your site. See [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates) and [Collection Templates](/documentation/view/collection-templates) for more information.
 
## Set up Collections
When you set up the rendering section for pages and collections:  
 - Set the existing `application.html` **layout** for every page and collection.  
 - Create a new unique **template** for each page.  
 - Create a new unique **template directory** for each collection.  
When you are get familiar with how pages and collections render, you can start to edit your project to more efficiently share layouts and templates accross pages and collections on your site. See [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates) and [Collection Templates](/documentation/view/collection-templates) for more information.
 
## Set up Relationships
Needs to be done after colletions are setup.
Can relate a collection to a page, or a collection to items in a collection. Cannot relate a page to a pge.
Add related datafields to pages and collections in order to set up the framework to create `one-to-many` relationships between pages and collections in your project. If you aren't sure what the relationships are for your project, you can come back to do this later. For more information about relationships, see the [Relationships](/documentation/view/relationships) Docs.

---

## Add Content
Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

## Start Developing
etc.
