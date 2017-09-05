# First Site Checklist
Complete this checklist after completing the Quickstart Guide. Each task is meant to introduce you to a new part of Airship file structure or the content management system, and challenge you to find relevant Documentation to help you complete the challenge. Once all items are checked, you should be fairly comfortable with basic Airship templating, rendering, asset management, and deployment patterns.

---

## Source Code Management
- [ ] If you haven't already, set up your site as a Git repository and commit your files.

## Layouts & Templates
- [ ] Move the contents of the embedded stylesheet located in the `application.html` into a `styles.css` external stylesheet located in the `/assets/` directory. Within the `application.html` layout, link to the external stylesheet. All files within the assets directory can be accessed with a link that starts with the relative reference `/assets/...`.

- [ ] In your local project directory, manually create a new **Layout** named `homepage.html` that is a copy of `application.html`, then in the Admin Portal, set it as the layout for the `root.html` page.

- [ ] In the Airship Admin Portal, add a new "About" page to the site. Set the layout for the new page to be `homepage.html` and set a new template called `about.html`.

- [ ] Edit the new `homepage.html` layout, so that it has a `<nav>` with a list of links to the root page and the about page.  Page links should always be relative to the subdomain, so instead of `<a href="http://localhost:9001/about">About</a>` or `<a href="https://mysite.airshipcms.io/about">About</a>`, set the link to be  `<a href="/about">About</a>`

- [ ] Git commit your files.

- [ ] In your terminal, run `airship land`. The CLI should show you a preview of the following actions that will happen:
 - layout `homepage.html` will be updated.
 - template `about.html` will be created.
 - asset `styles.css` will be deleted.
 
Since you have everything backed up with Git and you can retrieve the previous versions of files, go ahead and enter `y` to run the `airship land` command.

You will see that you probably have a version of the `homepage.html` layout that you _don't want_, and a brand new `about.html` template that you _do want_. Your `styles.css` has also been deleted, and you probably _don't want_ that change either.

Fix the unwanted changes in Git.
- [ ] Revert to the good version of the `homepage.html` layout.
- [ ] Retrive the `styles.css` file that was deleted.

Lessons: 
- Always back up files with Git. Airship commands are not meant to replace smart source code management tools that have features like merges and branch management. `airship land` should be reserved for syncing initial project files. Landing replaces _all local files_ with versions of files from the Airship server. `airship launch` should be reserved for deployment. Launching replaces _all live files_ with versions of files that you have locally. These actions are "all or nothing" so be very careful and conscious when running these commands.
- If you want to grab generated layouts and templates from the live Airship server, it really only makes the most sense to do so _at the very beginning of your project_ or _right after you have set up all the pages and collections for your project_. If you are midway through development, you typically don't want to run `airship land`. It is a better idea to manually create layouts & templates in your local project directory, and keep the best versions of files backed up with Git.

## Files & File Structure
