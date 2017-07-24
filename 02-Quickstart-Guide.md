Follow this Quickstart Guide to set up your first project with Airship CMS. 

Not quite ready to create a project yet? Just create a Free login at the [Airship CMS Developer Portal](https://skyport.airshipcms.io) then and try out the Developer Workflow and CLI tools using one of our [Open Source Demo Projects](#).

Note: In the following guide, replace all instances of "subdomain" with your actual subdomain for the site:  
- `https://subdomain.airshipcms.io`
- `https://subdomain.airshipcms.io/admin`
- `airship login subdomain`

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the [Airship CMS Developer Portal](https://skyport.airshipcms.io).
2. Check your email to verify your account, then log in to the [Airship CMS Developer Portal](https://skyport.airshipcms.io).
3. Choose a Plan and create your first project.
4. After a few minutes, you will receive a notification that your project is ready.
5. When you navigate to your project url `(https://subdomain.airshipcms.io)`, it will look something like this:  

![first-site-wider](https://user-images.githubusercontent.com/1865400/28547862-9d65786e-706c-11e7-9bc2-bc989dae7299.png)  

## 2. Install Airship Launcher CLI Tools.
Command line tools are currently available for _Mac_ and _Linux_ development environments. You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools.

**Quick Install**  
Easily install the command line tools by entering this into your terminal:
```
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
```

**Slow Install**  
Developers that want to see exactly what tools are being installed can read and follow the instructions at [install.airshipcms.io](https://install.airshipcms.io).

## 3. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
```
If you use a source code management tool like Git, then you can initialize this directory as a versioned project.

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
In a browser, navigate to `localhost:9001`. You will see actual site content, rendered with your local layouts, templates, and  assets. It should look exactly the same as the content on the live site:  

![first-site-wider](https://user-images.githubusercontent.com/1865400/28547862-9d65786e-706c-11e7-9bc2-bc989dae7299.png)  

## 8. Edit content.
In the Airship CMS admin panel for your site, go to the <img width="27" alt="pencil" src="https://user-images.githubusercontent.com/1865400/28548078-afea5594-706d-11e7-99e6-4d023d4bca84.png"> **Content Editing** section of the "Homepage" of your site, you will see all the dynamic content for the site:  

![page-edit](https://user-images.githubusercontent.com/1865400/28547379-4a21a35a-706a-11e7-875b-1b317bdf5185.png)

Edit some content and save the page. Wait a few seconds, then refresh both your live site url in one tab `(https://subdomain.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)` and you will see the content updates in both instances of the site, after a few seconds.

## 9. Edit templates & files.

### Render `{{{help}}}`.
Above the other html markup on the `root.html` template, add following markup:  
```
<div>
  {{{help}}}
</div>
<hr>
```

Then save the file and refresh the browser window. This will render a list of all data that is available for rendering on the page. In your browser, this will output the following list above all other page content:  

![help](https://user-images.githubusercontent.com/1865400/28548652-de46ac96-7070-11e7-8bba-32de4d1268b3.png)  

Items in this list are the variable names for data that can be rendered on the _root_ page. The items listed inside the `fields` property correspond to fields that are set for the _root_ page in the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> Page Modify section in Airship CMS admin:  

![page-setup](https://user-images.githubusercontent.com/1865400/28547380-4a2518c8-706a-11e7-8a9c-2652b4752009.png)  

Content from Airship CMS is rendered by adding markup with the exact variable name listed in the `{{{help}}}` list, contained by double curly braces. For example:
```
<h1>{{fields.header}}</h1>
```
Will output:
```
<h1>Airship CMS</h1>
```
Take a look at all the markup on the `root.html` template, and you can see which parts of the page are hardcoded in the markup, versus pulled from the CMS.

You can comment out or delete the help markup if you don't need it anymore. This list is meant to be a useful reference to help you while you are developing locally.

See the Airship Docs for more information about rendering for Layouts, Pages, and Collections.

## 10. `airship launch` to publish your project.
While you are working locally, you can add and edit templates, layouts, and files locally without affecting the live version of your site.

Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter `y` or `yes` and in seconds, your project will be published!

## 11. Back up files with your own source code management tool.
Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can store any extra source files you want in your project repository, as long as they are outside of the `compartments` directory.

Commit all Airship files with your project, including `compartments` and the `.airship` directory containing the `name` file.

---

# Buildinf your own Schema in Airship CMS.
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
