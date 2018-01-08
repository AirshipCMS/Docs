# 3. Local Development

For your first website, this checklist will help you to get oriented with the basics of local development using Airship CMS. Experienced developers might want to read more about Classic Rendering and SPA Rendering, or check out some example Starter Kits to see how Airship CMS can integrate with popular frontend frameworks such as Angular or ReactJS.

---

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

---

Next: Editing Content in Airship CMS

---

#### Skip to  
Developer Log in  

#### Developer Tools
CLI Commands  
CLI Troubleshooting  

#### Rendering
Classic Rendering  
SPA Rendering  


