Follow this Quickstart Guide to set up your first project with Airship CMS. Not ready to create a project yet? Just create a Free login, and try out the Developer Workflow and CLI tools using one of our Open Source Demo Projects.

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the _Airship CMS Developer Portal_.
2. Check your email to verify your account, then log in to the _Airship CMS Developer Portal_.
3. Choose a Plan and create your first project.
4. After a few minutes, you will receive a notification that your project is ready.

Links:
- Airship CMS Developer Portal

## 2. Install Airship Launcher CLI Tools.
Command line tools are currently available for _Mac_ and _Linux_ development environments. You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools.

**Quick Install**  
Easily install the command line tools by entering this into your terminal:
```
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
```

**Slow Install**  
Developers that want to see exactly what tools are being installed can read and follow the instructions at `install.airshipcms.io`.

Links:
- install.airshipcms.io

## 3. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
```
If you use an SCM like Git, then you can initialize this directory as a versioned project.

## 4. `airship login`to access your project content.
Navigate to your project directory:
```
cd ~/MyFirstAirshipSite
```
Inside your project directory, run this command (_replace "subdomain" with your actual subdomain_):
```
airship login subdomain
```
A browser window will pop up prompting you to login. Once you log in successfully, you can close the browser window.

## 5. `airship land` to retrieve files.
Inside of the `~/MyFirstAirshipSite directory`, run this command to download the base set of files that were generated when you set layouts and templates for your pages and collections:  
```
airship land
```  

This command will generate a `compartments`directory containing all the Airship files that are necessary for building out your project templates. 

## 6. `airship serve` to run your site locally.
Start a local development server by using the Airship Launcher serve command.
```
airship serve
```
Leave this terminal open during development in order to maintain an active connection to the airship server.

## 7. View your local site in a browser.
In a browser, navigate to `localhost:9001`. You will see actual site content, rendered with your local layouts, templates, and  assets.

## 8. Edit files & content.

### Render `{{{help}}}`.
Somewhere within the html markup of the `root.html` template, add the code `{{{help}}}`, then save the file and refresh the browser window. This will render a list of all data that is available for rendering on the page. For example, on the _root.html_ template, add this markup:
```
<div>
  {{{help}}}
</div>
```
This will output something similar to this:
```
<div>
<ul>
  <li>id</li>
  <li>site_id</li>
  <li>name</li>
  <li>permalink</li>
  <li>fields
    <ul>
      <li>header</li>
      <li>admin_portal_notes</li>
      <li>example_rendering</li>
      <li>setup_instructions[list]</li>
      <li>color_theme</li>
      <li>example_multiselect</li>
      <li>show_featured_project_example</li>
    </ul>
  </li>
  <li>related
    <ul>
      <li>related_items_example[list]</li>
    </ul>
  </li>
  <li>layout</li>
  <li>template</li>
  <li>published_on</li>
  <li>created_at</li>
  <li>updated_at</li>
  <li>slug</li>
</ul>
<div>
```
Items in the list are the variable names for properties that can be rendered on the template you are rendering. The items inside the `fields` property correspond to fields that were added to the _root_ page in Airship CMS.

### Render content.
To render content managed by Airship CMS, add markup with the exact variable name listed in the `{{{help}}}` list, contained by double curly braces. Example for the _root.html_ template:
```
<h1>{{name}}</h1>
```
This will output:
```
<h1>Landing Page</h1>
```
See the Airship Docs for more information about rendering for lists, pages, collections.

Links:
- Layouts
- Page Templates
- Collection Template Directories

### Edit templates, layouts, and files.
You can add and edit templates, layouts, and files locally without affecting the live version of your site. See the Airship Docs for more information about project directory structure and file types.

Links:
- Project Directory Structure

### Sync content managed by Airship CMS.
Content updated in the Airship CMS admin panel automatically syncs to your local development environment as long as `airship serve` is running.

## 10. `airship launch` to publish your project.
Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter `y` or `yes` and in seconds, your project will be published!

## 11. Back up files with your own source code management tool.
Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can store any extra source files you want in your project repository, as long as they are outside of the `compartments` directory.

Commit all Airship files with your project, including `compartments` and the `.airship` directory containing the `name` file.










## 2. Build your Schema in Airship CMS.
This section describes how to set up pages & collections for your project. By default, Airship Projects are set up with 1 demo page and 1 demo collection. You can skip Step #2, if you want to see what the example page and collection files look like. You can always r

1. **Create a Sitemap Sketch.** Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project.
2. **Create Pages & Collections.** 
 - Log in to the Airship CMS admin panel for your project.  
 - Modofu
 - Create the pages and collections for your project and define the dynamic datafields needed for each Page and Collection. Every datafield that you create directly maps to a piece of content or a value that you want to allow an admin to be able to edit. 
3. **Page & Collection Rendering.** When you set up the rendering section for pages and collections:  
 - Set the existing `application.html` **layout** for every page and collection.  
 - Create a new unique **template** for each page.  
 - Create a new unique **template directory** for each collection.  
You can also add **Related** datafields to pages and collections in order to set up the framework to create `one-to-many` relationships between pages and collections in your project.
4. **Add Content.** Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. _You need to add placeholder content so that something renders on the page when you run the site locally._

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
