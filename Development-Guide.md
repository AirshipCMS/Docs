# Development Guide
This development guide is for someone who has completed the [Schema Setup Guide](/documentation/view/schema-setup-guide) and is ready to start developing their site.

Before you can begin developing, make sure you have the Airship CLI Tools installed by navigating to a terminal and running the `airship` command. If you do not have them installed yet, check out the instructions on [Installing the Airship CLI Tools](/documentation/view/install-airship-cli-tools). Once your CLI tools are installed, feel free to briefly look over the available [commands](/documentation/view/airship-cli-commands) that may be used during development.

In order to become more familiar with the development workflow, it might be helpful to review how to [use layouts and templates](/documentation/view/using-layouts-templates), what the [project structure](/documentation/view/project-directory) is like, and how to use Airships [Propeller Helpers](/documentation/view/propeller-helpers) to render your site content.

---

## Develop Locally
Once you have your pages and collections set up in the Admin portal, you're ready to start developing!

The following is a step by step processes on what the development workflow is typically like for a simple site. For more examples, see the [Local Development Flows](/documentation/view/development-guide#user-content-local-development-flows) below.

### 1. Login
To begin developing, you must first [login](/documentation/view/airship-cli-commands#user-content-airship-login) to your site using your Super Admin credentials.

First, create or navigate to the desired project directory in your terminal. This is where all the files for your site will live locally.

Run the `airship login subdomain` command, where _subdomain_ is the subdomain of your site.

If this is a new directory, you will be asked to set the current directory to your sites project root. Enter `y` if this is okay.

After validating connection to your site, this will open a new window in your browser with a login prompt. Remember to login with your Super Admin credentials or you will not be able to land your site in the next step. Check out the [Airship CLI Troubleshooting Information](/documentation/view/airship-cli-troubleshooting) if you experience any authentication issues.

Once you have successfully authenticated, you're ready to [airship land](/documentation/view/airship-cli-commands#user-content-airship-land).

### 2. Land
To land your site, ensure you're in the projects root directory, then run `airship land`.

This will prompt whether or not it's okay to download the sites compartments to your local project directory. This includes all the files for your site, such as the layouts and templates created in the Admin portal.

Note: running `airship land` will overwrite anything you were working on locally that was not published to your site using `airship launch`. Be sure to backup files or use a source management tool to avoid losing any of your hard work!

Once you have downloaded your sites compartments, your [project directory](/documentation/view/project-directory) should look similar to the following:

```
.
├── .airship
│  └── name
└── compartments
   ├── airmail
   ├── assets
   │   ├── media
   │   ├── scripts
   │   └── styles
   ├── layouts
   │   └── application.html
   ├── partials
   └── templates
       └── root.html
```

You are now ready to [serve](/documentation/view/airship-cli-commands#user-content-airship-serve) your site locally and start developing!




Describe workflow more verbosely and with numbered step headers
- login
- serve
- develop (you might also be running other dev processes. see examples below)
- make backups/commit files
- launch

---

## Local Development Flows
Explain possibilities for Development flow. How you can put stuff outside the compartments directory. 

### Gulp Example
Explain a stack that uses gulp, scsss and node to build css and output into x directories.

### Angular Example
Explain what that might look like.

### React Example
Explain what that might look like.

### Design Files
Explain what that might look like.

### Source Code Management
Explain what that might look like.
