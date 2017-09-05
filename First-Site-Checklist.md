# First Site Checklist
Complete this checklist after completing the Quickstart Guide. Each task is meant to introduce you to a new part of Airship file structure or the content management system, and challenge you to find relevant Documentation to help you complete the challenge. Once all items are checked, you should be fairly comfortable with basic Airship templating, rendering, asset management, and deployment patterns.

---

## Source Code Management
- [ ] If you haven't already, set up your site as a Git repository and commit your files.

## Layouts & Templates
- [ ] In your local project, move the contents of the embedded stylesheet located in the `application.html` into a `styles.css` external stylesheet located in the `/assets/` directory within a subdirectory called `/styles`. Within the `application.html` layout, be sure to link to the external stylesheet. (All files within the assets directory can be accessed with a link that starts with the relative reference `/assets/...`).

- [ ] In your local project, manually create a new layout named `checklist-layout.html` that is a copy of `application.html`.

- [ ] In the Airship CMS Admin Portal, set `checklist-layout.html` as the layout for the `root.html` page.

- [ ] In the Airship CMS Admin Portal, add a new "About" page to the site. Set the layout for the new page to be `checklist-layout.html` and set a new template called `about.html`. You can add fields later. Save the page.

- [ ] Edit the new `checklist-layout.html` layout, so that it has a `<nav>` with links to the root page and the about page.  (Page links should always be relative to the subdomain, so instead of `<a href="http://localhost:9001/about">About</a>` or `<a href="https://mysite.airshipcms.io/about">About</a>`, set the link to be  `<a href="/about">About</a>`).

- [ ] Git commit your files.

## Land & Launch Conflicts
- [ ] In your terminal, run `airship land`.

The CLI should show you a preview of the following actions that will happen:
- layout `checklist-layout.html` will be updated.
- template `about.html` will be created.
- asset `styles.css` will be deleted.
 
- [ ] Since you have everything backed up with Git and you can retrieve the previous versions of files, enter `y` to run the `airship land` command and perform the changes.

After running `airship land`, you will probably end up with:
- changes to `homepage.html` layout that you _don't want_
- a brand new `about.html` template that you _do want_
- deletion of `styles.css`that you _don't want_

### Fix changes in Git
- [ ] Revert to the good version of the `homepage.html` layout.
- [ ] Retrieve the `styles.css` file that was deleted.
- [ ] Commit the new `about.html` template.

- [ ] Run `airship launch` to publish all your _good_ changes.

### Lessons: 

Always back up files with Git. Airship commands are not meant to replace smart source code management tools that have features like merges and branch management. `airship land` replaces _all local files_ with versions of files from the Airship server so it should only be reserved for syncing initial project files. `airship launch` replaces _all live files_ with versions of files that you have locally, so it should be reserved only for deployment. These actions are "all or nothing" so be very careful and conscious when running these commands.

It really only makes sense to run `airship land` **once**, _at the very beginning of your project_ or _right after you have set up all the pages and collections for your project_. If you are midway through development, you typically don't want to run `airship land`. If you create pages and collections midway through development, you can set the templates and layouts in the Admin Portal, though it is a better idea to manually create layouts & templates in your local project directory, rather than run `airship land` to pull down generated files.

Again: Always back up files with Git!

## Image Assets
- [ ] Place an image into the `/assets/` directory, within an `/images/` subdirectory.
- [ ] Include the image with an `<img>` tag somewhere on the root page. (Reference the file with the relative reference `/assets/images/...`).
- [ ] Commit your changes.
- [ ] Launch your changes.

Files in the `/assets/` directory are specifically for development. As a developer, you can reference files and make changes to them, however users with "Admin" access won't be able to add/edit/delete any files within this directory.

Unlike files uploaded through the Admin Portal, files launched trhough the CLI  are _not optimized_ , so it is important to manually keep file sizes optimized.

## Page Modify: Editing a Field
- [ ] _Modify_ the Abut Page, and add a new field called "Header", type "Text". _Edit_ the page to add some placeholder content, then _Render_ the field content on the About Page template.
- [ ] _Modify_ the Abut Page, and change the label for the "Header" field to "Title". Notice that the label for the field changes on the _Edit_ view, however the original variable name `header` does not change.

Lesson: The text label for a field can be edited so it displays with a different label in the Admin Edit view, however the variable name and type cannot be changed once they are set. (You have to delete the original field and add a new field if you really want a different variable name).

## Page Modify: Add More Fields
