# Development Guide
This development guide is for someone who has completed the [Schema Setup Guide](https://airshipcms.io/documentation/view/schema-setup-guide) and is ready to start developing their site.

Before you can begin developing, make sure you have the Airship CLI Tools installed by navigating to a terminal and running the `airship` command. If you do not have them installed yet, check out the instructions on [Installing the Airship CLI Tools](https://airshipcms.io/documentation/view/install-airship-cli-tools). Once your CLI tools are installed, feel free to briefly look over the available [Airship CLI Commands](https://airshipcms.io/documentation/view/airship-cli-commands) that may be used during development.

In order to become more familiar with the development workflow, it might be helpful to review how to [Use Layouts & Templates](https://airshipcms.io/documentation/view/using-layouts-templates), what the [Project Structure](https://airshipcms.io/documentation/view/project-directory) is like, and how to use Airships [Propeller Helpers](https://airshipcms.io/documentation/view/propeller-helpers) to render your site content.

To view some sample projects with different development workflows, check out the [Boilerplates & Examples](https://airshipcms.io/documentation/view/boilerplates-examples) in our Docs.

---

## Develop Locally
Once you have your pages and collections set up in the Admin portal, you're ready to start developing! 

The following is the general development workflow for a simple website.

### 1. Login
To begin developing, you must first [`airship login`](https://airshipcms.io/documentation/view/airship-cli-commands#user-content-airship-login) to your site using your Superadmin credentials.

First, create or navigate to the desired project directory in your terminal. This is where all the files for your site will live locally.

Run the `airship login mysite` command, where _mysite_ is the subdomain of your site.

If this is a new directory, you will be asked to set the current directory to your sites project root. Enter `y` if this is okay.

After validating connection to your site, this will open a new window in your browser with a login prompt. Remember to login with your Superadmin credentials or you will not be able to land your site in the next step. Check out the [Airship CLI Troubleshooting Information](https://airshipcms.io/documentation/view/airship-cli-troubleshooting) if you experience any authentication issues.

### 2. Land

#### Continuing Projects
You can skip `airship land` if you are continuing work on an existing project. You are probably using an SCM tool or some other means to back up files, so the only commands you really need are `airship serve` to serve files, and `airship launch` to publish files.

#### New Projects
Once you have successfully authenticated, you're ready to `airship land` your new project. First, ensure that you are in the project root directory, then run `airship land`.

This will ask you if it is okay to download the site compartments to your local project directory. This includes all the files for your site, such as the layouts and templates created in the Admin portal.

**Note**: Running `airship land` will overwrite anything you were working on locally that was not published to your site using `airship launch` or backed up with source code management. Be sure to your backup files or use a source management tool to avoid losing any of your hard work!

Once you have downloaded your sites compartments, your [Project Directory](https://airshipcms.io/documentation/view/project-directory) should look similar to the following:

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

### 3. Serve
To view what your site looks like locally, run `airship serve` in your projects root directory, then navigate to `http://localhost:9001` in your browser.

This will render any changes you have locally that are not necessarily published on the site. When you make changes, you typically won't have to restart the server. However, if the server must be restarted, simply exit the terminal process and rerun the `airship serve` command.

### 4. Developing
Make changes to files within the `/compartments/templates` directory and save, then refresh the page in your browser at `http://localhost:9001` to see the update.

Any changes made locally to files and templates won't be published on your actual site until you explicitly run the `airship launch` command. Changes made in the Admin portal, however, will be immediately visible on your and launched site.

You can customize your development workflow to use pre-processors, scss, Angular, React, node, and many other frontend tools. As long as the output files end up in `/compartments/templates` and `/compartments/assets` you are good to go. For more extensive applications, you will need to set up SPA Routes in the Admin Panel to create custom handlers for page routing. 

To view some examples of development workflow, check out the [Boilerplates & Examples](https://airshipcms.io/documentation/view/boilerplates-examples) in our Docs.

### 5. Launch
When you are ready to publish changes to your live site at `http://mysite.airshipcms.io`, remember to back up your files, then run the `airship launch` command in your project root directory.

This will show a list of actions being requested to update the live site, then show a prompt to publish those changes. Enter `y`.

That's it! Your site changes will be launched to `http://mysite.airshipcms.io`.
