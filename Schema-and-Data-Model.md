
# Building your own Schema in Airship CMS
Once you are familiar with the Airship development workflow, you can modify the fields on the demo page, and delete the demo collection that comes with a new project, and start creating your own project schema.

---

1. **Create a Sitemap Sketch.** Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project. If items from one section should feed into another section, map out those relationships as well.

2. **Create Your Pages & Collections.** 
 - Log in to the Airship CMS admin panel `(https://subdomain.airshipcms.io/admin)` for your project.  
 - Modify the "Homepage" fields to change what shows for the root page of your site.
 - Create additional pages and collections for your project and define the dynamic datafields needed for each Page and Collection. 
 
3. **Page & Collection Rendering.** When you set up the rendering section for pages and collections:  
 - Set the existing `application.html` **layout** for every page and collection.  
 - Create a new unique **template** for each page.  
 - Create a new unique **template directory** for each collection.  
 
4. Add **Related** datafields to pages and collections in order to set up the framework to create `one-to-many` relationships between pages and collections in your project.

5. **Add Content.** Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

Use Case Links:
- Demo Use Cases
- Demo Schemas

Airship CMS Links:
- Pages
- Collections
- Relationships

Templating Links:
- Layouts
- Page Templates
- Collection Templates
