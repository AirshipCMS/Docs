# First Site Checklist
Complete this checklist after completing the Quickstart Guide. Each task is meant to introduce you to a new part of Airship file structure or the content management system, and challenge you to find relevant Documentation to help you complete the challenge. Once all items are checked, you should be fairly comfortable with basic Airship templating, rendering, asset management, and deployment patterns.

---

## Source Code Management
- [ ] Set up your site as a Git repository and commit your files.

## Layouts
- [ ] In your local project, manually create a new layout named `checklist-layout.html` that is a copy of `application.html`.
- [ ] Move the contents of the embedded stylesheet located in the `checklist-layout.html` into a `styles.css` external stylesheet located in the `/assets/` directory within a subdirectory called `/styles`. Within the `checklist-layout.html` layout, be sure to link to the external stylesheet. (All files within the assets directory can be accessed with a link that starts with the relative reference `/assets/...`).
- [ ] In the Airship CMS Admin Portal, set `checklist-layout.html` as the layout for the `root.html` page.
- [ ] Git commit your files.

## Pages & Navigation
- [ ] In the Airship CMS Admin Portal, add a new "About" page to the site. Set the layout for the new page to be `checklist-layout.html` and set a new template called `about.html`. Skip the fields section for now. Save the page.
- [ ] In your local project, manually create a new template named `about.html` to match the file set in the Airship CMS Admin Portal.
- [ ] Edit the `checklist-layout.html` layout, so that it has a `<nav>` with links to the homepage and about page.  (Page links should always be relative to the subdomain, so instead of `<a href="http://localhost:9001/about">About</a>` or `<a href="https://mysite.airshipcms.io/about">About</a>`, set the link to be  `<a href="/about">About</a>`).
- [ ] Git commit your files.

## Image Assets
- [ ] Place an image into the `/assets/` directory, within an `/images/` subdirectory.
- [ ] Include the image with an `<img>` tag somewhere on the root page. (Reference the file with the relative reference `/assets/images/...`).
- [ ] Git commit your files.

Files in the `/assets/` directory are specifically for development. As a developer, you can reference files and make changes to them, however users with "Admin" access won't be able to add/edit/delete any files within this directory.

Unlike files uploaded through the Admin Portal, files launched trhough the CLI  are _not optimized_ , so it is important to manually keep file sizes small and optimized.

## Page Modify: Editing a Field Name
- [ ] _Modify_ the Abut Page, and add a new field called "Header", type "Text". _Edit_ the page to add some placeholder content, then _Render_ the field content on the About Page template.
- [ ] _Modify_ the Abut Page, and change the label for the "Header" field to "Title". Notice that the label for the field changes on the _Edit_ view, however the original variable name `header` does not change.

The text label for a field can be edited so it displays with a different label in the Admin Edit view, however the variable name and type cannot be changed once they are set. (You have to delete the original field and add a new field if you really want a different variable name).

### Text & Text Area
- [ ] Delete the "Title" field.
- [ ] Add "Company Name" field type "text".
- [ ] Edit the page and save some placeholder content.
- [ ] Render the field content on the About page.
- [ ] Git Commit your changes.

### Richtext Area
- [ ] Add "Company Background" field type "richtext area"
- [ ] Edit the page and save some placeholder content.
- [ ] Render the field content on the About page. Be sure to use triple curly brackets since the field contains html markup.
- [ ] Git Commit your changes.

### Image
- [ ] Add "Company Photo" field type "image"
- [ ] Edit the page and save a placeholder image with a title, subtitle, and caption.
- [ ] Render the field content on the About page. Be sure to use an `{{#each}}` propeller helper to render the image.
- [ ] Be sure to use the `{{secure_url}}` property instead of `{{url}}` for the most secure delivery of content.
- [ ] Git Commit your changes.

### List of Images
- [ ] Add "Employees" field type "list of images"
- [ ] Edit the page and save some placeholder images with a title, subtitle, and captions.
- [ ] Render the field content on the About page. Be sure to use an `{{#each}}` propeller helper to render the images.
- [ ] Be sure to use the `{{secure_url}}` property instead of `{{url}}` for the most secure delivery of content.
- [ ] Git Commit your changes.

### Link & List of Links
- [ ] Add "Favorite Places" field type "list of links"
- [ ] Edit the page and save some placeholder links with a title, subtitle, url, and captions.
- [ ] Render the field content on the About page. Use an `{{#each}}` propeller helper.
- [ ] Git Commit your changes.

### Date
- [ ] Add "Year Started" field type "date"
- [ ] Edit the page and save a date.
- [ ] Render the field content on the About page. Use a `{{format_date}}` helper to render the date.
- [ ] Git Commit your changes.

---

## Handling Land & Launch Conflicts

- [ ] In your terminal, run `airship land`.

The CLI should show you a preview of the following actions that will happen:
- layout `checklist-layout.html` will be updated.
- template `about.html` will be created.
- asset `styles.css` will be deleted.
 
Since you have everything backed up with Git and you can retrieve the previous versions of files, enter `y` to run the `airship land` command and perform the changes.

After running `airship land`, you will probably end up with:
- changes to the `checklist-layout.html` that you _don't want_
- changes to the `about.html` template that you _don't want_
- deletion of `styles.css`, and an image that you _don't want_

### Fix Changes in Git & Launch
- [ ] Revert changes to the `homepage.html` layout and `about.html` template.
- [ ] Retrieve deleted files.
- [ ] Run `airship launch` to publish all your _good_ changes.

Always back up files with Git. Airship commands are not meant to replace smart source code management tools that have features like merges and branch management. `airship land` replaces _all local files_ with versions of files from the Airship server so it should only be reserved for syncing initial project files. `airship launch` replaces _all live files_ with versions of files that you have locally, so it should be reserved only for deployment. These actions are "all or nothing" so be very careful and conscious when running these commands.

It really only makes sense to run `airship land` **once**, _at the very beginning of your project_ or _right after you have set up all the pages and collections for your project_. If you are midway through development, you typically don't want to run `airship land`. If you create pages and collections midway through development, you can set the templates and layouts in the Admin Portal, though it is a better idea to manually create layouts & templates in your local project directory, rather than run `airship land` to pull down generated files.

Again: Always back up files with Git!

---

That's it! Checklist Complete!
