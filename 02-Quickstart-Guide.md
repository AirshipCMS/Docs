Follow this Quickstart Guide to set up your first project with Airship CMS. Not ready to create a project yet? Just create a Free login, and try out the Developer Workflow and CLI tools using one of our Open Source Demo Sites.

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the _Airship CMS Developer Portal_.
2. Check your email to verify your account, then log in to the _Airship CMS Developer Portal_.
3. Choose a Plan and create your First Site.
4. After a few minutes, you will receive a notification that your site is ready, and you can log in to your site's Airship CMS admin panel.

Links:
- Airship CMS Developer Portal

## 2. Build your Schema in Airship CMS.
1. **Sketch a Plan.** Before you start setting up anything in the CMS, sketch a sitemap of key pages, collections, and data on each page and collection in your project.
2. **Set up Collections.** In the Airship CMS admin panel, create the pages and collections for your project and define the dynamic datafields needed for each Page and Collection. Any datafield that you create directly maps to a piece of content or a value that the Content Creator can update.
3. **Create Relationships.** When you add a **Related** datafield to a page or collection, this sets up the framework to create `one-to-many` relationships between pages and collections in your project.
4. **Add Content.** Add some placeholder content to each page field on your pages, and add items with placeholder content to each collection.

Links:
- Demo Use Cases
- Sketches to Case Studies of Complex Custom Products
- Setting up a Page
- Setting up a Collection
- Creating Relationships

## 3. Install Airship Launcher CLI Tools.
Command-line development tools are currently available for _Mac_ and _Linux_. Install the Airship Launcher so you have access to the command line tools necessary for serving site content when you are developing locally. You can skip this step if you already have airship launcher installed. Not sure? Type <span class="code">airship version</span> in your terminal. If you see a version number, you are already good to go!

**Quick Install**  
Easily install the command line tools by entering this into your terminal:
```
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
```

**Slow Install**  
For those of you that want to see exactly what tools are being installed on your machine, read and follow the instructions at <span class="code">install.airshipcms.io</span>.

Links:
- install.airshipcms.io

## 4. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
cd ~/MyFirstAirshipSite
```
If you use an SCM like Git (you should be!), then you can initialize this directory as a versioned project.

## 5. <span class="code">airship login</span> to access your project content.
Inside of the <span class="code">~/MyFirstAirshipSite directory</span>, run this command (replace "subdomain" with your actual subdomain:
```
airship login subdomain
```
A browser window will pop up prompting you to login through Auth0 (our authentication provider). Once you log in successfully, you can close the browser window.

## 6. <span class="code">airship land</span> to retrieve files.
Inside of the <span class="code">~/MyFirstAirshipSite directory</span>, run this command to sync your local project directory with the templates that were generated when you set up your site schema in Airship CMS:
```airship land```
This command will generate a <span class="code">compartments</span> directory containing all the Airship files that are necessary for building out your project templates. Running <span class="code">airship land</span> will overwrite any files in the <span class="code">compartments</span> directory, so please be very aware of when you run this command, and back up local files often! You will typically only need to <span class="code">airship land</span> once per project during this setup phase. After your files are landed, you will be working locally on your project for a while (and hopefully backing up code to an SCM), so you probably won't need to land the project again.

## 7. <span class="code">airship serve</span> to serve your site locally.
You can start a local development server by using the Airship Launcher serve command.
```
airship serve
```
You need to leave this terminal open during development in order to keep an active connection to the airship server.

## 8. View your local site in a browser.
In a browser, navigate to <span class="code">localhost:9001</span>. You will see actual site content, rendered with your local development files.

## 9. Edit files & content.

### Render {{{help}}}.
Within the html markup on any layout or template, add the markup <span class="code">{{{help}}}</span> and save the file to render a list of all data that is available for displaying on athe specific layout or template. Example on the _root.html_ template:
```
{{{help}}}
```
This will output something like this:
```
- id
- site_id
- name
- permalink
- fields
  - header
  - body
  - ...
- layout
- template
- published_on
- created_at
- updated_at
- slug
```

### Render content.
To render content, add markup with the exact variable name listed in the <span class="code">{{{help}}}</span>, contained by double curly braces. Example on the _root.html_ template:
```
<h1>{{name}}</h1>
```
This will output:
```
<h1>Landing Page</h1>
```
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
```airship launch```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter <span class="code">y</span> or <span class="code">yes</span> and in seconds, your site will be published!

## 11. Back up files with your own source code management tool.
Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can put any files you want in your main repository directory, as long as the <span class="code">compartments</span> directory maintains proper files and structure.
