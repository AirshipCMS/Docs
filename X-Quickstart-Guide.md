# Quickstart 

(These are the steps. They need to be fleshed out with paragraph descriptions. No intro needed. Each section should have a link to an appropriate page with more information.)

## 1. Start a Project.

If you don't have a free Airship account yet, sign up at (Skyport)[https://skyport.airshipcms.io].
Skyport is where you go to create and manage all your Airships.
Launch a new Airship Site, then follow the link on your confirmation email to login to the Airship Admin panel.
The Airship Admin panel is the CMS where you would manage your users (accounts for content creators or other developers), and design the structure of the site.

-- link to Setting up a Project page.

## 2. Build your schema & relationships.  

If you already have a version of your wireframes and sitemap then you can start defining each [Page](https://airshipcms.io/docs/page) and [Collection](https://airshipcms.io/docs/collections) that you'll need. When thinking about what [Fields](https://airshipcms.io/docs/field) a [Page](https://airshipcms.io/docs/page) or [Collection](https://airshipcms.io/docs/collections) might need, remember that any [Field](https://airshipcms.io/docs/field) that you define should be some piece of content or value that you would want your [Content Creator](https://airshipcms.io/docs/content-creator) to be able to update by themselves at any time.
If you aren't sure about what the structure of your site is yet, or what [Fields](https://airshipcms.io/docs/field) you'll need, don't worry, just start with the first page, your [Landing Page](https://airshipcms.io/docs/root-page) (this is the first page that is initialized with every new site) and just one [Collection](https://airshipcms.io/docs/collections) that you know you'd need. If you are making an E-Commerce site, then create a [Collection](https://airshipcms.io/docs/collections) named "Products". If you have a site that has a blog, then create a [Collection](https://airshipcms.io/docs/collections) named "Posts".
Then just start with [Templating](https://airshipcms.io/docs/propellers) and as you build out the [Layouts](https://airshipcms.io/docs/propellers/layouts) and [Templates](https://airshipcms.io/docs/propellers/templates) you can mark areas that you want to be dynamic fields and update the schema later. Implement your initial designs, update the schema, add lipsum to the CMS, then continue iterating in this fasion. You don't have to have all the answers now, Airship will help you define the schema and relationships as you build out the site or application. 
It's easier to start by building your own, though you could look at our [Sample Projects](https://airshipcms.io/docs/sample-projects) for some inspiration.

-- Describe in brief, and link to Schema & Data Model section of docs.  

## 3. Install Airship Launcher

_You can skip this if you already have it installed._
_not sure? type this in your terminal, does it work?_ `airship version`

Whether you chose to build out your initial site schema or not, you can still move on to the next steps, there is no single structured way to start. When you go to your newly launched Airship Site, install the [Airship Launcher](/docs/airship-launcher) 

### TL;DR Quick Install

```sh
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
```

### Slow Install

_Show me what's going on_

Read and follow the instructions at [install.airshipcms.io](https://install.airshipcms.io)


## 4. `airship login` to access your project content.

Use the [Airship Launcher](/docs/airship-launcher) to login and start developing your Site locally.

First, create a new empty directory in your [Terminal](/docs/help/terminal).

```sh
mkdir ~/MyFirstAirshipSite
cd ~/MyFirstAirshipSite
```

_if you use an [SCM](/docs/help/scm) like [Git](/docs/help/git) (and you should!) then you can initialize this directory as a versioned project._

inside of the `~/MyFirstAirshipSite` directory

```sh
airship login yourairshipsubdomain
```

This will start the authentication process for logging in to your Airship Site identified by the subdomain that you chose when you created your Airship Site.

A browser window should pop up prompting you to login throuh Auth0 (our authentication provider). Once you log in successfully, you can close the browser window (the green checkmark will prompt you to close it).



-- link to Setting up a Projec to page and Airship CLI section of docs.  

## 5. `airship land` to retrieve files.  

Once you are logged in, sync your local project directory with the templates and files from Airship.

_All of the airship commands should be done insid of your `~/MyFirstAirshipSite` directory_

```sh
airship land
```

This command will sync down all the files stored on Airship servers to your local dev environment, overwriting any files that you have in this project directory (which is why using an [SCM](/docs/help/scm) is so important!)

Now that you have all the files that were on the server, you can start developing!

-- link to Airship CLI section of docs.  

## 5. `airship serve` for local development.  

You can start a local development server by using the Airship Launcher `serve` command.

```sh
airship serve
```

You must leave this terminal open during development in order to access the local server, so you probably want to have at least two terminals open.


-- and link to Airship CLI section of docs.  

## 6. Change files & link to content fields.  

While the server is running, you can test out your site locally by navigating to [localhost:9001](http://localhost:9001)

The local development site pulls live content from the Airship Site, so internet access is required.

You can add and update [Layouts](https://airshipcms.io/docs/propellers/layouts), [Templates](https://airshipcms.io/docs/propellers/templates), and [Media Assets](https://airshipcms.io/docs/media-assets) during development, refresh the local server, and see the local changes right away.

-- and link to Rendering & Templates section of docs.  

## 7. `airship launch` to publish your project.  

Once you feel like a version of the site is ready to launch to production, deploy your templates and assets with your live Airship Site.

```sh
airship launch
```

You'll be presented with a preview of the actions that will occur. Review the actions **carefully** before confirming the launch, the actions are **not undo-able** 

Once you confirm and launch, then your site will be updated immediately.

-- link to Airship CLI section of docs.  

## 8. Back up files with your own source code management tool.  

We know that you have your own workflow, and that it is best practice to use a [Source Code Manager](/docs/help/scm).
You will maintain your own versioning and your own backups. Airship will host the version of your site that you tell it to by landing and launching.

It is also good practice to have a staging environment, which is really simple with Airship. Just create a new Airship site for each environment that you need for Quality Assurance, User Acceptance Testing, and Production. 

Describe in brief.  
