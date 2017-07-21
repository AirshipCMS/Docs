Follow this Quickstart Guide for setting up your first site with Airship CMS. Not ready to create a site yet? Just create a Free login, and try out the Developer Workflow and CLI tools using one of our Open Source Demo Sites.

---

## 1. Start a Project.
1. Sign up for a free Airship account to access the _Airship CMS Developer Portal_.
2. Check your email to verify your account, then log in to the _Airship CMS Developer Portal_.
3. Create your First Site.
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
Command-line development tools are currently available for _Mac_ and _Linux_. Install the Airship Launcher so you have access to the command line tools necessary for serving site content when you are developing locally. You can skip this step if you already have airship launcher installed. Not sure? Type `airship version` in your terminal. If you see a version number, you are already good to go!

**Quick Install**  
Easily install the command line tools by entering this into your terminal:
<pre>
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
</pre>

**Slow Install**  
For those of you that want to see exactly what tools are being installed on your machine, read and follow the instructions at `install.airshipcms.io`.

Links:
- install.airshipcms.io

## 4. <span class="code">airship login</span> to access your project content.
<p>Create a new empty directory for your project.</p>
<pre>
mkdir ~/MyFirstAirshipSite
cd ~/MyFirstAirshipSite
</pre>
<p>If you use an SCM like Git (you should be!), then you can initialize this directory as a versioned project.</p>
<p>Inside of the <span class="code">~/MyFirstAirshipSite directory</span>, run this command (replace "yourairshipsubdomain" with your actual subdomain:</p>
<pre>
airship login yourairshipsubdomain</span>
</pre>
<p>A browser window will pop up prompting you to login through Auth0 (our authentication provider). Once you log in successfully, you can close the browser window.</p>

## 5. <span class="code">airship land</span> to retrieve files.
<p>Once you are logged in, you need to sync your local project directory with the templates and files generated when you set up your site schema in Airship CMS. All airship commands should be done inside of your <span class="code">~/MyFirstAirshipSite</span> directory.</p>
<pre>airship land</pre>
<p>This command will generate a <span class="code">compartments</span> directory containing critical Airship files that are necessary for building out your project templates. Running <span class="code">airship land</span> will overwrite any files in the <span class="code">compartments</span> directory, so please be very aware of when you run this command, and back up local files often! You will typically only need to <span class="code">airship land</span> once per project during this setup phase. After your files are landed, you will be working locally on your project (and hopefully backing up code to an SCM), so you probably won't need to land the project again.</p>
<p>Now that you have synced all the files that were on the server, you can start developing!</p>

## 6. <span class="code">airship serve</span> for local development.
<p>You can start a local development server by using the Airship Launcher serve command.</p>
<pre>
airship serve
</pre>
<p>You must leave this terminal open during development in order to access the local server, so you probably want to have at least two terminals open.
</p>

## 7. Change files & link to content fields.
<p>While the server is running, you can test out your site locally by navigating to <span class="code">localhost:9001</span>.
<p>The local development site pulls live content from the Airship database, so internet access is required.</p>
<p>You can add and update layouts, templates, and media assets during development, refresh the local server, and see the local changes right away.</p>

## 8. <span class="code">airship launch</span> to publish your project.
<p>Once a version of your site is ready to launch to production, run this command to deploy your templates and assets:</p>
<pre>airship launch</pre>
<p>In your terminal, you will be presented with a preview of the actions that will occur when you run <span class="code">airship launch</span>. Review the actions carefully before confirming, then enter <span class="code">y</span> or <span class="code">yes</span>.
<p>Once you confirm and launch, then your site will be updated immediately!</p>

## 9. Back up files with your own source code management tool.
<p>Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can put any files you want in your main repository directory, as long as the <span class="code">compartments</span> directory maintains proper files and structure.</p>
<p>Another good practice during development, is to have a staging environment. This is relatively simple with Airship. Just create a new Airship site for each environment that you need for Quality Assurance, User Acceptance Testing, and Production. For sites that have a more complex eCommerce functionality that requires a lot of testing, we have a separate staging server that is set to the development mode of Stripe.</p>
