# Development Guide
This development guide is for someone who has completed the [Schema Setup Guide](/documentation/view/schema-setup-guide) and is ready to start developing their site.

Before you can begin developing, make sure you have the Airship CLI Tools installed by navigating to a terminal and running the `airship` command. If you do not have them installed yet, check out the instructions on [Installing the Airship CLI Tools](/documentation/view/install-airship-cli-tools). Once your CLI tools are installed, feel free to briefly look over the available [commands](/documentation/view/airship-cli-commands) that may be used during development.

In order to become more familiar with the development workflow, it might be helpful to review how to [use layouts and templates](/documentation/view/using-layouts-templates), what the [project structure](/documentation/view/project-directory) is like, and how to use Airships [Propeller Helpers](/documentation/view/propeller-helpers) to render your site content.

---

## Develop Locally
Once you have your pages and collections set up in the Admin portal, you're ready to start developing!

The following is a step by step processes on what the development workflow is typically like for a simple site. For more examples, see different [Project Examples](/documentation/view/development-guide#user-content-project-examples) below.

### 1. Login
To begin developing, you must first [login](/documentation/view/airship-cli-commands#user-content-airship-login) to your site using your Superadmin credentials.

First, create or navigate to the desired project directory in your terminal. This is where all the files for your site will live locally.

Run the `airship login subdomain` command, where _subdomain_ is the subdomain of your site.

If this is a new directory, you will be asked to set the current directory to your sites project root. Enter `y` if this is okay.

After validating connection to your site, this will open a new window in your browser with a login prompt. Remember to login with your Superadmin credentials or you will not be able to land your site in the next step. Check out the [Airship CLI Troubleshooting Information](/documentation/view/airship-cli-troubleshooting) if you experience any authentication issues.

Once you have successfully authenticated, you're ready to [airship land](/documentation/view/airship-cli-commands#user-content-airship-land).

### 2. Land
To land your site, ensure you're in the projects root directory, then run `airship land`.

This will prompt whether or not it's okay to download the sites compartments to your local project directory. This includes all the files for your site, such as the layouts and templates created in the Admin portal.

**Note**: running `airship land` will overwrite anything you were working on locally that was not published to your site using `airship launch`. Be sure to your backup files or use a source management tool to avoid losing any of your hard work!

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

You are now ready to [serve](/documentation/view/airship-cli-commands#user-content-airship-serve) your site locally.

### 3. Serve
To view what your site looks like locally, run `airship serve` in your projects root directory, then navigate to `http://localhost:9001` in your browser.

This will render any changes you have locally that are not necessarily published on the site. When you make changes, you typically won't have to restart the server. However, if the server must be restarted, simply exit the terminal process and rerun the `airship serve` command.

You are now ready to start developing your site.

### 4. Developing
To start developing your site, make a change to the `root.html` file within the `/compartments/templates` directory and save, then refresh the page in your browser at `http://localhost:9001` to see the update.

Any changes made locally are viewable when running `airship serve`, and won't be published on your actual site until you explicitly run the [`airship launch`](/documentation/view/airship-cli-commands#user-content-airship-launch) command. Changes made in the Admin portal, however, will be available on your public site immediately.

To view some examples of development workflow, check out the below [Project Examples](/documentation/view/development-guide#user-content-project-examples), or any of the [Boilerplates & Examples](/documentation/view/boilerplates-examples) from our Docs.

### 5. Launch
When you are ready to publish the new changes to your live site at `http://yoursubdomain.airshipcms.io`, remember to back up your changes, then run the `airship launch` command in your projects root directory.

This will show a list of actions being requested to update the live site, then prompt whether or not it's okay to make those changes. Enter `y` if these are okay.

You should now be able to see your most recent changes at `http://yoursubdomain.airshipcms.io`.

Check out the documentation for more information about the [`airship launch`](/documentation/view/airship-cli-commands#user-content-airship-launch) command.

---

## Example Projects
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
