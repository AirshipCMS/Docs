Follow this Quickstart Guide to set up your first project with Airship CMS. Not quite ready to create a project yet? Take a look at some of our [Featured Projects](https://airshipcms.io/featured-projects) &amp; [Open Source Demos & Boilerplates](https://airshipcms.io/documentation/view/boilerplates-examples).

In the following guide, be sure to replace all instances of "mysite" with your actual subdomain for the site:  
- `https://mysite.airshipcms.io`
- `https://mysite.airshipcms.io/admin`
- `airship login mysite`

---

## 1. Log in to your site.
1. Airship is currently available by Private Invitation Only! Request a [Test Pilot's License](https://airshipcms.io/signup), and we will contact you when a seat opens up! 

2. Once we set up a site for you, navigate to your project url `(https://mysite.airshipcms.io)`. It will look something like this:  

<img width="500" alt="Browser Initial" src="https://airshipcms.io/assets/media/quickstart-guide/tiny-browser-initial.jpg">

2. Log in to your project admin `(https://mysite.airshipcms.io/admin)`, and check that your login & password work.

<img width="500" alt="CMS Login" src="https://airshipcms.io/assets/media/quickstart-guide/cms-login.jpg">

Once you log in successfully, you should see a welcome message:

<img width="500" alt="CMS Dashboard" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-dashboard.jpg">

## 2. Install Airship Launcher CLI Tools.
Command line tools are available for Mac, Linux, and Windows(beta). You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools. See the Install page for [_Mac_ and _Linux_](https://airshipcms.io/mac-linux-installer) or [Windows](https://airshipcms.io/windows-installer) (beta).

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
A browser window will pop up prompting you to login.

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/auth0-login.jpg">

Once you log in successfully, you can close the browser window. Your terminal should read:
```
Successful Authentication.
```

## 5. `airship land` to retrieve files.
Inside of the `~/MyFirstAirshipSite directory`, run this command to download the base set of files that were generated when you set layouts and templates for your pages and collections:  
```
airship land
```  
This command will generate a `compartments` directory containing very basic Airship files that are necessary for building out your project templates. 

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

<img width="500" alt="Text Editor Initial" src="https://airshipcms.io/assets/media/quickstart-guide/tiny-terminal-initial.jpg">

## 6. `airship serve` to run your site locally.
Start a local development server by using the Airship Launcher serve command.
```
airship serve
```
Leave this terminal open during development in order to maintain an active connection to the airship server.

## 7. View your local site in a browser.
In a browser, navigate to `localhost:9001`. You will see actual site content, rendered with your local layouts, templates, and  assets. It should look exactly the same as the content on the live site:  

<img width="500" alt="Browser Initial" src="https://airshipcms.io/assets/media/quickstart-guide/tiny-browser-initial.jpg">

## 8. Edit the Homepage content. See it update locally & live.
Go to the Airship CMS admin panel for your site, and click the pencil icon <img width="27" alt="pencil" src="https://user-images.githubusercontent.com/1865400/28548078-afea5594-706d-11e7-99e6-4d023d4bca84.png"> to edit the content on the "Homepage" of your site. It should look like this:  

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-initial.jpg">

Edit content. Save the page. Wait a few seconds, then refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)`. You will see the content update in both instances of the site. Sometimes it takes a few refreshes or a hard refresh to show content changes.

## 9. Edit the Homepage template. See it update locally (and _not_ update live).
Back in your text editor, open the `root.html` template located in `/compartments/templates`. Edit some static text on the file. Save the file.

Refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)` and you will see the markup changes only update in the _local instance of your site_. This is because in your local site, the page is rendered based on **local files** & **published content**, whereas the published site renders **published files** & **published content**. 

### 10. See available properties for a page with `{{{help}}}`.
On the `root.html` template and add following markup at the very top of your page. Save the file.
```
{{{help}}}
```
In SublimeText 3, it will look like this:

<img width="500" alt="Text Editor Help" src="https://airshipcms.io/assets/media/quickstart-guide/tiny-terminal-help.jpg">

In your browser, refresh your local site url `(http://localhost:9001)` and you will see a list of properties:  

<img width="500" alt="Browser Help" src="https://airshipcms.io/assets/media/quickstart-guide/tiny-browser-help.jpg">

Items in this list are the variable names for data that can be rendered on the _root_ page. The items listed inside the `fields` property correspond to fields that are set for the _root_ page in the <img width="26" alt="wrench" src="https://user-images.githubusercontent.com/1865400/28548077-afe52966-706d-11e7-93f0-ce9e958ec070.png"> Page Modify section in Airship CMS admin:  

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modify.jpg">

Content from Airship CMS is rendered by adding markup with the exact variable name listed in the `{{{help}}}` list, contained by double curly braces. For example:
```
<h1>{{fields.header}}</h1>
```
Will output:
```
<h1>Airship CMS</h1>
```
Take a look at all the markup on the `root.html` template, and you can see which parts of the page are hardcoded in the markup, versus pulled from the CMS.

You can comment out or delete the help markup if you don't need it anymore. This list is meant to be a useful reference to help you while you are developing locally. `{{{help}}}` will not render anything on published sites.

## 11. Change the page & add more pages.
Review Docs on [Page Templates](https://airshipcms.io/documentation/view/page-templates) and [Page Properties](https://airshipcms.io/documentation/view/page-properties) for details on how to set a page template and how to render fields and properties on a page. Some things you can try:
- Add new fields through the CMS, and add markup to render the data on the `root.html` template. 
- Add assets to the `/assets/` directory and link to them in your template or through a stylesheet.
- Add more pages.
- Add a global nav of links to your new pages in the [Layout](https://airshipcms.io/documentation/view/layouts).

## 13. `airship launch` to publish your project.
Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

In your terminal, you will be presented with a preview of the actions that will occur. Review the actions carefully before confirming. When you are ready, enter `y` or `yes` and in seconds, your project will be published!

---

## Next Steps
After testing the very basic development cycle, you can start building more complex projects!

### Source Code Management
Part of your regular development workflow probably involves using a Source Code Management tool like [Git](https://github.com), where you can maintain your own versioning and backups of files. SCM tools work seamlessly with Airship projects. You can also store any extra source files you want in your project repository, as long as all non-essential files are located outside of the `compartments` directory.

When you use a SCM tool, commit all Airship files with your project, including `compartments` and the `.airship` directory.

### Project Schema
Study how [Pages](/documentation/view/pages), [Collections](https://airshipcms.io/documentation/view/collections), and [Relationships](https://airshipcms.io/documentation/view/relationships) work to form the [Schema & Data Model](https://airshipcms.io/documentation/view/schema-and-data-model) of a project built with Airship. Then follow the [Schema Setup Guide](https://airshipcms.io/documentation/view/schema-setup-guide) to turn your project plan into an actual project.

### Templating
Learn more about [Layouts](https://airshipcms.io/documentation/view/layouts), [Page Templates](https://airshipcms.io/documentation/view/page-templates), and [Collection Templates](https://airshipcms.io/documentation/view/collection-templates).

### XHR, Angular, React, and Single-Page Applications
If you want to build a custom javascript component that requires an XHR request, or if you prefer to build a component or even the entire project as a Single-Page Application using [React](https://facebook.github.io/react/), [Angular](https://angular.io/), [Angular 1.x](https://angularjs.org/), or any other frontend framework, check out some of our [Featured Projects](https://airshipcms.io/featured-projects) &amp; [Open Source Demos & Boilerplates](https://airshipcms.io/documentation/view/boilerplates-examples) that use React & Angular. You will need to access the [Airship API](https://airshipcms.io/documentation/view/introduction-to-airship-api) to build custom applications that access Airship CMS content. We will be launching Swagger Documentation for all API endpoints in September 2017. In the meantime, contact us to get the most up-to-date list of API endpoints.
