NOTES!
- Open Source projects can be downloaded, though you won't yet be able to locally run them. We are still building out 'open source viewing' capabilities.
- The Airship CMS Developer Portal is in a private beta, so you won't be able to do Step 1. If you would like a demo website, contact us and we will be happy to set up a demo site for you!

---

Follow this Quickstart Guide to set up your first project with Airship CMS. 

Not quite ready to create a project yet? Just create a Free login at the [Airship CMS Developer Portal](https://skyport.airshipcms.io) then and try out the Developer Workflow and CLI tools using one of our [Open Source Demo Projects](/documentation/view/boilerplates-examples).

In the following guide, replace all instances of "mysite" with your actual subdomain for the site:  
- `https://mysite.airshipcms.io`
- `https://mysite.airshipcms.io/admin`
- `airship login mysite`

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the [Airship CMS Developer Portal](https://skyport.airshipcms.io).
2. Check your email to verify your account, then log in to the [Airship CMS Developer Portal](https://skyport.airshipcms.io).
3. Choose a Plan and create your first project.
4. After a few minutes, you will receive a notification that your project is ready.
5. When you navigate to your project url `(https://mysite.airshipcms.io)`, it will look something like this:  

<img width="500" alt="new-teal-site" src="https://user-images.githubusercontent.com/1865400/29647018-8cb91908-8822-11e7-8664-b284a7def4f5.jpg">

## 2. Install Airship Launcher CLI Tools.
Command line tools are available for Mac, Linux, and Windows(beta). You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools. See the Install page for [_Mac_ and _Linux_](/mac-linux-installer) or [Windows](/windows-installer) (beta).

## 3. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
```
If you use a source code management tool like Git, then you can initialize this directory as a versioned project.

## 4. `airship login` to access your project content.
Navigate to your project directory:
```
cd ~/MyFirstAirshipSite
```
Inside your project directory, run this command (_replace "mysite" with your actual subdomain_):
```
airship login mysite
```
A browser window will pop up prompting you to login. Once you log in successfully, you can close the browser window.

## 5. `airship land` to retrieve files.
Inside of the `~/MyFirstAirshipSite directory`, run this command to download the base set of files that were generated when you set layouts and templates for your pages and collections:  
```
airship land
```  
This command will generate a `compartments`directory containing all the Airship files that are necessary for building out your project templates. 

## 6. Open your local files in a text editor.
Open your entire directory in a text editor. This Quickstart Guide uses [SublimeText 3](https://www.sublimetext.com/3). Your local directory structure should look something like this:
```
.
├── .airship
│  └── name
└── compartments
   ├── airmail
   ├── assets
   ├── layouts
   │   └── application.html
   ├── partials
   └── templates
       └── root.html
```
In SublimeText 3 it looks like this:

<img width="500" alt="sublime" src="https://user-images.githubusercontent.com/1865400/29646676-98367020-8820-11e7-81c8-4f4f92e9eb9f.jpg">

## 6. `airship serve` to run your site locally.
Start a local development server by using the Airship Launcher serve command.
```
airship serve
```
Leave this terminal open during development in order to maintain an active connection to the airship server.

## 7. View your local site in a browser.
In a browser, navigate to `localhost:9001`. You will see actual site content, rendered with your local layouts, templates, and  assets. It should look exactly the same as the content on the live site:  

<img width="500" alt="new-teal-site" src="https://user-images.githubusercontent.com/1865400/29647018-8cb91908-8822-11e7-8664-b284a7def4f5.jpg">

## 8. Edit content. See it update locally & live.
Go to the Airship CMS admin panel for your site, and click the pencil icon <img width="27" alt="pencil" src="https://user-images.githubusercontent.com/1865400/28548078-afea5594-706d-11e7-99e6-4d023d4bca84.png"> to go to the content editing section of the "Homepage" of your site. It should look like this:  

<img width="500" alt="airshipcms" src="https://user-images.githubusercontent.com/1865400/29646793-36ffe1e6-8821-11e7-9e7a-b14379517277.png">

Edit some content. Save the page. Wait a few seconds, then refresh both your live site url in one tab `(https://subdomain.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)` and you will see the content updates in both instances of the site, after a few seconds.

## 9. Edit the Homepage template. See it update locally (and _not_ update live).
Back in your text editor, open the `root.html` template located in `/compartments/templates`. This template contains the markup that renders on the Homepage of your site. Edit some static text on the file. Save the file.

Refresh both your live site url in one tab `(https://subdomain.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)` and you will see the markup changes only update in the _local instance of your site_. This is because in your local site, the page is rendered based on **local files & live content**, compared to the published site where the page is rendered based on **live files & live content**. How do you upload your local files to your live site? We will get there soon!

### 10. Render `{{{help}}}` on a template to see a list of data.
On the `root.html` template, replace the header test you did in #9 and add following markup:  
```
<!--start test-->
{{{help}}}
<hr>
<!--end test-->
```
In SublimeText 3, it will look like this:

![help-root](https://user-images.githubusercontent.com/1865400/28699367-c7d8e75a-72e4-11e7-916b-271a62b36cd8.png)

Be sure your file is Saved. Then, refresh your local site url `(http://localhost:9001)` and you will see a list of properties. In your browser, it will look like this:  

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

You can comment out or delete the help markup if you don't need it anymore. This list is meant to be a useful reference to help you while you are developing locally. In fact, `{{{help}}}` will not render anything when you launch a site. It will only render a list of properties in local development.

## 11. Change the Root Page

### Change the Root Page.
See what you can change about the Page Template. Add some fields, change the markup. For more detailed information on each property and datafield type that can be rendered on a page, see the [Page Templates](/documentation/view/page-templates) Docs.

### Change the Layout.
(@TODO: Layout Quickstart)
See the Airship Documentation for what can be rendered on [Layouts](/documentation/view/layouts).

### Change the Collection.
(@TODO: Collection Quickstart)
See the Airship Documentation for what can be rendered on [Collection Templates](/documentation/view/collection-templates).

## 12. `airship launch` to publish your project.
Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter `y` or `yes` and in seconds, your project will be published!

---

## What's Next?
(@TODO)

### Source Code Management
Part of your regular development workflow probably involves using a Source Code Management tool like [Git](https://github.com), where you can maintain your own versioning and backups of files. SCM tools work seamlessly with Airship projects. You can also store any extra source files you want in your project repository, as long as all non-essential files are located outside of the `compartments` directory.

When you use a SCM tool, commit all Airship files with your project, including `compartments` and the `.airship` directory.

### Templating
From here you might want to learn more about [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates), and [Collection Templates](/documentation/view/collection-templates).

### Project Schema
Study how [Pages](/documentation/view/pages), [Collections](/documentation/view/collections), and [Relationships](/documentation/view/relationships) work to form the [Schema & Data Model](/documentation/view/schema-and-data-model) of a project built with Airship. Then follow the [Schema Setup Guide](/documentation/view/schema-setup-guide) to turn your project plan into an actual project.

### XHR, Angular, React, and Single-Page Applications
(describe) Some projects may not need classic website rendering, or Classic Rendering is not able to handle complex logic. For the most power, it is useful to combine classically rendered page elements with client-side rendered components. 

If you want to use Airship CMS more like a headless CMS to construct your database/project schema and then build your application using a framework like Angular or React, then see the (Something Guide) and some of our Demo Projects.
