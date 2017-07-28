## Schema Setup Guide
This schema setup guide is for someone who has completed the [Quickstart Guide](/documentation/view/quickstart-guide) and is ready to set up their first actual project. 

Before starting, be sure to study how [Pages](/documentation/view/pages), [Collections](/documentation/view/collections), and [Relationships](/documentation/view/relationships) work to form the [Schema & Data Model](/documentation/view/schema-and-data-model) of a project built with Airship.

---

## Remove the Demo Content
The `root` page is the only page you cannot delete in an Airship project. 
modify the demo fields on the **Homepage**, and delete the demo collection. 
,
 and start creating your own pro
# Building your own Schema i
# Building your own Schema in Airship CMS
Once you are familiar with the Airship development workflow, you can modify the fields on the demo page, and delete the demo collection that comes with a new project, and start creating your own project schema.

---

1. **Create a Sitemap Sketch.** 
Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project. If items from one section should feed into another section, map out those relationships as well.

2. **Create Your Pages & Collections.** 
 - Log in to the Airship CMS admin panel `(https://subdomain.airshipcms.io/admin)` for your project.  
 - Modify the "Homepage" fields to change what shows for the root page of your site.
 - Create additional [Pages](/documentation/view/pages) and [Collections](/documentation/view/collections) for your project and define the dynamic datafields needed for each Page and Collection. 
 
3. **Page & Collection Rendering.** 
When you set up the rendering section for pages and collections:  
 - Set the existing `application.html` **layout** for every page and collection.  
 - Create a new unique **template** for each page.  
 - Create a new unique **template directory** for each collection.  
When you are get familiar with how pages and collections render, you can start to edit your project to more efficiently share layouts and templates accross pages and collections on your site. See [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates) and [Collection Templates](/documentation/view/collection-templates) for more information.
 
4. **Relationships.**
Add related datafields to pages and collections in order to set up the framework to create `one-to-many` relationships between pages and collections in your project. If you aren't sure what the relationships are for your project, you can come back to do this later. For more information about relationships, see the [Relationships](/documentation/view/relationships) Docs.

5. **Add Content.** 
Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

@KELLI Add Use Case Links:
- Demo Use Cases
- Demo Schemas
n Airship CMS
Once you are familiar with the Airship development workflow, you can modify the fields on the demo page, and delete the demo collection that comes with a new project, and start creating your own project schema.
