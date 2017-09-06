Follow this Quickstart Guide to set up your first project with Airship CMS. Not quite ready to create a project yet? Take a look at some of our [Featured Projects](https://airshipcms.io/featured-projects) &amp; [Open Source Demos & Boilerplates](https://airshipcms.io/documentation/view/boilerplates-examples).

[ VIDEO ]

---

In the following guide, be sure to replace all instances of "mysite" with your actual subdomain for the site:  
- `https://mysite.airshipcms.io`
- `https://mysite.airshipcms.io/admin`
- `airship login mysite`

---

## 1. Create your site.
_Note: Airship is currently available by Private Invitation only. You won't yet be able to login at the developer portal. Request a [Test Pilot License](https://airshipcms.io/signup), and we will contact you when a seat opens up!_

Create a new Airship site at the Airship Developer Portal.

<img width="500" alt="Skyport Developer Portal" src="https://airshipcms.io/assets/media/quickstart-guide/skyport.jpg">

Once your site is provisioned, navigate to your project url `(https://mysite.airshipcms.io)`. It will look something like this:  

<img width="500" alt="Browser Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-initial.jpg">

## 2. Log in to your site.
Log in to the admin portal `(https://mysite.airshipcms.io/admin)` with your login credentials.

<img width="500" alt="CMS Login" src="https://airshipcms.io/assets/media/quickstart-guide/cms-login.jpg">

Once you log in successfully, you should see a welcome message:

<img width="500" alt="CMS Dashboard" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-dashboard.jpg">

Keep this window open. You will need to access it later.

## 3. Install Airship Launcher CLI Tools.
Command line tools are available for Mac, Linux, and Windows(beta). You must install the Airship Launcher in order to be able to login and sync files between your local development environment and the Airship server. Non-developer admins and content creators don't need to install the CLI tools. See the Install page for [_Mac_ and _Linux_](https://airshipcms.io/mac-linux-installer) or [Windows](https://airshipcms.io/windows-installer) (beta) install instructions.

You only need to install the CLI tools once on your machine. If you have already done this, you can skip this step.

## 4. Create a local directory for your project.
Create a new empty directory for your project.
```
mkdir ~/MyFirstAirshipSite
```
If you use a source code management tool like Git, you can initialize this directory as a versioned project. Commit all files, including the hidden `.airship` directory.

## 5. `airship login` to access your project content.
Navigate to your project directory:
```
cd ~/MyFirstAirshipSite
```
Inside your project directory, run this command (_replace "mysite" with your actual subdomain_):
```
airship login mysite
```

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-02-logging-in.jpg">

A browser window will pop up prompting you to login.

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/auth0-login.jpg">

Once you log in successfully, you can close the browser window. Your terminal should read:
```
Successful Authentication.
```

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-03-logged-in.jpg">

## 6. `airship land` to retrieve files.
Inside of the `~/MyFirstAirshipSite directory`, run this command to download the base set of files that were generated when you set layouts and templates for your pages and collections:  
```
airship land
```  

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-04-land.jpg">

Enter `y` to the prompt.

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-05-landing.jpg">

Running `airship land` will generate a `compartments` directory containing very basic Airship files that are necessary for building out your project templates. 

<img width="500" alt="Auth0 Popup" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-06-landed.jpg">

## 7. Open your local files in a text editor.
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

<img width="500" alt="Text Editor Initial" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-initial.jpg">

## 8. `airship serve` to run your site locally.
Start a local development server by using the Airship Launcher serve command.
```
airship serve
```

<img width="500" alt="Text Editor Initial" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-07-serve.jpg">

Leave this terminal open during development in order to maintain an active connection to the airship server.

## 9. View your local site in a browser.
In a browser, navigate to `localhost:9001`. You will see actual site content, rendered with your local layouts, templates, and  assets. It should look exactly the same as the content on the live site:  

<img width="500" alt="Browser Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local.jpg">

## 10. Edit the Homepage content. See it update locally & live.
Go to the Airship CMS admin panel for your site, and click on "Pages" in the sidebar.

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-pages.jpg">

Click the pencil icon <img width="27" alt="pencil" src="https://airshipcms.io/assets/media/quickstart-guide/icon-pencil.png"> for the "Homepage" of your site. It should look like this:  

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-initial.jpg">

Edit content. 

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-edit.jpg">

Save the page. Wait a few seconds, then refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)`. You will see the content update in both instances of the site. Sometimes it takes a few refreshes or a hard refresh to show content changes.

Local Site: 

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-edit-content.jpg">

Live Site:

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-live-edit-content.jpg">

## 11. Edit the Homepage template. See it update locally (and _not_ update live).
Back in your text editor, open the `root.html` template located in `/compartments/templates`. Edit the button text. Save the file.

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-edit-template.jpg">

Refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)`. 

Local Site:

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-edit-template.jpg">

Live Site (same as before):

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-live-edit-content.jpg">

You will see that the markup has changed only in the _local instance of your site_. This is because in your local site, the page is rendered based on **local files** & **published content**, whereas the published site renders **published files** & **published content**. 

## 12. See available properties and fields for a page with `{{{help}}}`.
On the `root.html` template add following markup at the very top of your page. Save the file.
```
{{{help}}}
```
In SublimeText 3, it will look like this:

<img width="500" alt="Text Editor Help" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-help.jpg">

In your browser, refresh your local site url `(http://localhost:9001)` and you will see a list of properties:  

<img width="500" alt="Browser Help" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-help.jpg">

Items in this list are the variable names for data that can be rendered on the _root_ page. The items listed inside the `fields` property correspond to fields that are set for the _root_ page in the <img width="26" alt="wrench" src="https://airshipcms.io/assets/media/quickstart-guide/icon-wrench.png"> Page Modify section in Airship CMS admin:  

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modify.jpg">

Content from Airship CMS is rendered by adding markup with the exact variable name listed in the `{{{help}}}` list, contained by double curly braces.

## 13. Add a new field to the page.

### Add a New Field
On the Page Modify view in Airship CMS admin, add a new field to the page. This example adds the field `New Box`, type `text`.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modify-add-field.jpg">

Once the field is added to the list of fields, it will look like this:

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modified.jpg">

Save the Modify view. If you refresh any browsers (locally or live), the new field _will not show_ because it has no value set, and it has not been added to the page markup.

### Add a Value for the New Field
Click the pencil icon <img width="27" alt="pencil" src="https://airshipcms.io/assets/media/quickstart-guide/icon-pencil.png"> for the "Homepage". Add some text for the new field "New Box":

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-new-box.jpg">

### Refresh the browser for your local site
Refresh the browser for the local site. You will see the new field "new_box" added to the list of available page properties.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-help-new-box.jpg">

### Add markup for the new field
In your text editor, add markup to render the new field content:
```
{{fields.new_box}}
```

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-help-new-box.jpg">

You can comment out or delete the help markup if you don't need it anymore. The help list is meant to be a useful reference to help you while you are developing locally. `{{{help}}}` will not render anything on published sites.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-new-box.jpg">

### Refresh the browser for your local site
Refresh the browser for the local site. You will now see the content rendered for the new field.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-new-box.jpg">

If you refresh the browser for the live site, you won't see the new field. You will need to run `airship launch` to make your changes live.

## 14. `airship launch` to publish your project.
Once you are ready to launch your site, run this command to upload your local templates, layouts, and files to the live airship server:
```
airship launch
```

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-08-launch.jpg">

When you are ready, enter `y` or `yes` to launch the project. In seconds, your project will be published!

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/site-terminal-09-launched.jpg">

Refresh the browser for the live site, and it should match your local site.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/browser-live-new-box.jpg">

---

## You're Done!
That's all it takes to edit content, create pages, and publish a project! From here, it's up to you to decide how small or large you want to make your project!

### New Developers:
Brand new developers are encouraged to clone a repository follow the guide for building a sample project. See our examples of a Classically-Rendered Site or Classically-Rendered Blog:
- [Classically-Rendered Site](https://classic-rendering.airshipcms.io/)
- [Classically-Rendered Blog](https://classic-blog.airshipcms.io/)

Once you have built a clone of one of the demo sites, review the First Site Checklist to make sure you are comfortable with rendering and file management. 
- [First Site Checklist](https://airshipcms.io/documentation/view/first-site-checklist)

### Experienced Developers:
Once you have familiarized yourself with the basic land/serve/launch development cycle and have reviewed Airship [Documentation](https://airshipcms.io/documentation/view/introduction), you can build much more complex projects using the Airship API. Many Airship Developers use client-side frameworks and libraries with Airship CMS, or utilize `gulp` or `npm` processes to create custom development workflows that dynamically render content from the CMS. 

Airship is compatible with javascript frameworks such as [React](https://facebook.github.io/react/), [Angular](https://angular.io/), and [Angular 1.x](https://angularjs.org/), so you can build project components or entire sites that use client-side rendering alongside classically-rendered templating. Study the [Airship API](https://airshipcms.io/documentation/view/introduction-to-airship-api) or recreate one of our examples projects built as a javascript single-page application that pulls content from the CMS:
- [Angular 1.X](https://angular-1.airshipcms.io/)
- [Angular 1.x + Gulp + Babel + Airship CMS](https://angular-1-gulp-babel.airshipcms.io/)
- [Angular 4](https://angular-app.airshipcms.io/)
- [React](http://react-app.airshipcms.io/)
