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

## Create a New Page (Superadmins Only)
To create a new page, click the New Page button at the top right of the Pages section in Airship CMS. 

#### Title
This is the identifier for the page.

#### Permalink
The permalink is the identifier for page following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. By default, the permalink is generated from the Title except that it contains only lowercase letters, numbers, underscores, and dashes. You may also modify the permalink to change the default value. 

Example:
If you choose the title "About the Company" , the permalink will then become `about-the-company`, and the page is accessible at `http://yourwebsitename.com/about-the-company`.

### Page Rendering
The values set for Layouts and Templates correspond to the html files that are used to render the page.

#### Layout
A layout is the outer HTML wrapper of content on an Airship site. The layout usually contains static content that is repeated across many pages of a site (such as headers, navigation bars, or footers). A single layout can be used for multiple pages and collections on an Airship site. For more information, see [Layouts](/documentation/view/layouts).

Choose an existing layout, or create a new one.

When you create a new layout, it will automatically be generated on the Airship Server. When you execute the command `airship land` the file will download to the `/compartments/layouts/` directory.

#### Template
A template contains markup unique to the page. Templates can display page properties and fields that are set for the page. For more information, see [Page Templates](/documentation/view/page-templates).

Choose an existing template, or create a new one.

When you create a new template, it will automatically be generated on the Airship Server. When you execute the command `airship land` the file will download to the `/compartments/templates/` directory.

### Page Fields
The Page Fields section displays data specific to the page. There are four properties that are created by default and cannot be removed: `ID`, `Created At`, `Updated At`, and `Title`.

When you add custom fields, each field requires a `Title`, `Variable Name`, and `Type`. The order of these datafields can be changed by dragging and dropping each field into the desired order.

#### Title
The `Title` is the identifier for the field. When editing the content for a page, this displays as the label directly above the field input.

#### Variable Name
The `Variable Name` is the same as the Title, but only_contains lowercase letters, numbers, and underscores. The variable name is not editable, and is the identifier used when rendering the content from each field when using [Propeller Helpers](/documentation/view/propeller-helpers).

#### Type
The `Type` of the field sets what content fields display in the CMS.

For more information on datafields and example uses, see the documentation on [Datafields](/documentation/view/datafields).

---

## Modify Page (Superadmins Only)
To change properties and fields for a page, click the [ICON] Modify icon of the page you want to modify. 
Make changes to the page fields and properties and click the `Modify Page` button.

## Edit Page (Admins & Superadmins)
To edit the content entered for any page field, click the [ICON] Edit Content icon of the page you would like to edit.
Make changes to the page content and click either the `Save` or the `Save & Close` button.

## Delete Page (Superadmins Only)
To delete a page, click the [ICON] Modify icon of the page you want to modify. 
At the bottom of the page, click the `Delete Page` link. When prompted, click `Confirm Delete`.
