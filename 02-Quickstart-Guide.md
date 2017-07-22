Follow this Quickstart Guide to set up your first project with Airship CMS. Not ready to create a project yet? Just create a Free login, and try out the Developer Workflow and CLI tools using one of our Open Source Demo Sites.

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the _Airship CMS Developer Portal_.
2. Check your email to verify your account, then log in to the _Airship CMS Developer Portal_.
3. Choose a Plan and create your first project.
4. After a few minutes, you will receive a notification that your project is ready.

Links:
- Airship CMS Developer Portal

## 2. Build your Schema in Airship CMS.
1. **Sketch a Schema.** Before you set up anything in the CMS, sketch a sitemap of key pages, collections, and the data contained on each page and collection of your project.
2. **Set up Collections.** Log in to the Airship CMS admin panel for your project. Create the pages and collections for your project and define the dynamic datafields needed for each Page and Collection. Any datafield that you create directly maps to a piece of content or a value that you want to allow an admin to be able to edit.
3. **Create Relationships.** When you add a **Related** datafield to a page or collection, this sets up the framework to create `one-to-many` relationships between pages and collections in your project.
4. **Add Content.** Add some placeholder content to each page you created, and add items with placeholder content to every collection you created. You need placeholder content so that something renders on the page when you run the site locally.

Links:
- Demo Use Cases
- (Demo Schemas)
- Setting up a Page
- Setting up a Collection
- Creating Relationships

## 3. Install Airship Launcher CLI Tools.
Command-line tools are currently available for _Mac_ and _Linux_ development environments. You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools.

**Quick Install**  
Easily install the command line tools by entering this into your terminal:
```
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
```

**Slow Install**  
Developers that want to see exactly what tools are being installed can read and follow the instructions at <span class="code">install.airshipcms.io</span>.

Links:
- install.airshipcms.io

## 4. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
```
If you use an SCM like Git (you should be!), then you can initialize this directory as a versioned project.

## 5. <span class="code">airship login</span> to access your project content.
Navigate to your project directory:
```
cd ~/MyFirstAirshipSite
```
Inside your project directory, run this command (replace "subdomain" with your actual subdomain:
```
airship login subdomain
```
A browser window will pop up prompting you to login through Auth0 (our authentication provider). Once you log in successfully, you can close the browser window.

## 6. <span class="code">airship land</span> to retrieve files.
Inside of the <span class="code">~/MyFirstAirshipSite directory</span>, run this command to download the base set of files generated from your site schema:  
```
airship land
```  

This command will generate a <span class="code">compartments</span> directory containing all the Airship files that are necessary for building out your project templates. 

Running <span class="code">airship land</span> will overwrite any files in the <span class="code">compartments</span> directory, so be very careful when you run this command.

Using Git? If you are working on a team and another developer has already landed and committed the base project files, you don't need to run <span class="code">airship land</span>. Just be sure you have navigated to the root directory of your project before running the next step.

## 7. <span class="code">airship serve</span> to serve your site locally.
Start a local development server by using the Airship Launcher serve command.
```
airship serve
```
Leave this terminal open during development in order to maintain an active connection to the airship server.

## 8. View your local site in a browser.
In a browser, navigate to <span class="code">localhost:9001</span>. You will see actual site content, rendered with your local development files.

## 9. Edit files & content.

### Render {{{help}}}.
Within the html markup of any layout or template, add the code <span class="code">{{{help}}}</span>, then save the file and refresh the browser window displaying <span class="code">localhost:9001</span>. This will render a list of all data that is available for rendering on the specific layout or template you are editing. Example for the _root.html_ template:
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
      <li>body</li>
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

### Render content.
To render content managed by Airship CMS, add markup with the exact variable name listed in the <span class="code">{{{help}}}</span> list, contained by double curly braces. Example for the _root.html_ template:
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
You can add and edit templates, layouts, and files locally without affecting the live version of your site.

Links:
- Project Directory Structure

### Edit Content.
Content updated in the Airship CMS admin panel automatically syncs to your local development environment as long as <span class="code">airship serve</span> is running.

## 10. <span class="code">airship launch</span> to publish your project.
Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter <span class="code">y</span> or <span class="code">yes</span> and in seconds, your site will be published!

## 11. Back up files with your own source code management tool.
Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can put any files you want in your main repository directory, as long as the <span class="code">compartments</span> directory maintains proper files and structure.
