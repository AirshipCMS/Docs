# Pages
In Airship, a page represents **a single instance of a set of data**. 

In the context of a website, an Airship Page directly translates to a page of the website. 

[image] 

In the context of a web application, it's useful to use a page to contain some data that you want to allow a content manager to edit, even though that content shows up in just a small part of the application. Using Airship API you can access the page data and display the content from the CMS within your app. 

[image] 

---

## View All Pages
To view all of the pages within the site, navigate to the Admin panel, then click the Pages link on the sidebar at the left. 

### Root Page
Each site includes a default "Homepage". The permalink for this page is always `__root__`. This cannot be modified. 

## Create a New Page (superadmin)
To create a new page, click the New Page button at the top right of the Pages section in Airship CMS. 

#### Title
This is the identifier for the page.

#### Permalink
The permalink is the identifier for page following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. By default, the permalink is generated from the Title except that it contains only lowercase letters, numbers, underscores, and dashes. You may also modify the permalink to change the default value. 

For example, if you choose the title `About the Company`, the permalink will then become `about-the-company`, and the page is accessible at `/yourwebsitename.com/about-the-company`.

Example:
If you choose the title "About the Company" , the permalink will then become `about-the-company`, and the page is accessible at `http://yourwebsitename.com/about-the-company`.

### Page Rendering
The values set for Layouts and Templates correspond to the html files that are used to render the page.

#### Layout
A layout is the outer HTML wrapper of content on an Airship site. The layout usually contains static content that is repeated across many pages of a site (such as headers, navigation bars, or footers).

A single layout can be used for multiple pages and collections on an Airship site.

By default, `application.html` layout and `root.html` template are set as the defaults for the `__root__` page.

#### Template
A `template` contains markup unique to the page. Templates can page properties and fields that are set for the page.

#### Set a Layout and Template
Choose an existing layout and template, or create new ones.

Any files that are listed in the dropdowns will be automatically created in your project's `/compartments/layouts/` and `/compartments/templates/` directories when you execute the `airship land` command in your terminal.

For more information, see [Layouts](/documentation/view/layouts) and [Page Templates](/documentation/view/page-templates).

### Page Fields
The Page Fields section includes a variety of datafields to use in order to start creating page content. There are four fields that are created by default and cannot be modified: ID, Created At, Updated At, and Title.

When adding new fields, each field requires a Title, Variable Name, and Type. The order of these datafields can be changed by dragging each field into the proper position.

The Title is the identifier for the field. When editing the Page, each field will have this identifier directly above the field input.

The Variable Name is the same as the Title, but _only_ contains lowercase letters, numbers, dashes, and underscores. The variable name is not editable, and is the identifier used when rendering the content from each field when using [Propeller Helpers](/documentation/view/propeller-helpers).

The Type of the field is optional and varies from text inputs to lists of images.

For more information and example usages, see the documentation on [Datafields](/documentation/view/datafields).

---

## Modify Page (Superadmins Only)
In order to change the title, permalink, layout, template, or fields on a page, you must Modify the page. To change field content, see the [Edit Page](/documentation/view/pages#user-content-edit-page) section for more information.

To modify a page, navigate to `Pages` within Admin from the sidebar at the left, and click the wrench tool icon on the page you would like to modify. The `Modify` tab at the top right should be the active tab, and the page title at the top should now include the text `(Modify)`. This page can also be reached from the Edit Page tab by clicking the Modify tab.

Be sure to click the `Modify Page` button at either the top or bottom of the page after making all desired changes.

## Edit Page (Admins)
To edit the content entered for any page field, navigate to `Pages` within Admin from the sidebar at the left, and click the pencil icon on the page you would like to edit.

The `Edit Page` tab at the top right should be the active tab, and the page title at the top should now be preceded by the text `Edit Page:`. This page can also be reached from the Modify Page tab by clicking the Edit Page tab.

To save your changes, use either the `Save` button, or the `Save & Close` button. Use `Save` if you would just like to quickly save your changes without leaving the Edit Page. Use the `Save & Close` button to save and return to the `Pages` page. 

## Delete Page (Superadmins Only)
To delete a page, navigate to the Modify page for the page you would like to delete.

At the bottom of the page, click the `Delete Page` link. When prompted, click `Confirm Delete`.

For more information about navigating to the Modify Page, see the [Modify Page section](/documentation/view/pages#user-content-modify-page).
