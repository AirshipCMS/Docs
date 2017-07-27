# Pages
In Airship CMS, each website has a _Homepage_ page created by default. The permalink for this page is always `__root__` and **cannot** be modified.

To view all of the pages within the site, navigate to the Admin panel, then click the `Pages` link on the sidebar at the left. Ensure that you have the proper access rights and contacting the site owner if necessary.


## Create Page
To create a new page, navigate to `Pages` within Admin from the sidebar at the left, then click the `New Page` button at the top right.

### Page Setup
The first property to fill out is the `Title` under `Page Setup`. This will be the identifier for this page. You may also manually enter the `Permalink` as well, though by default it is the same as the Title but with only lowercase letters, numbers, underscores, and dashes.

For example, if you choose the title `About the Company`, the permalink will then become `about-the-company`, and the page is accessible at `/yourwebsitename.com/about-the-company`.


### Page Layout & Template
Under this section, there are two dropdowns: Layout and Template. By default, an `application.html` layout and `root.html` template are created for each site, and is used by the Homepage page that is also created by default.

A single layout can be used for multiple templates. The layout file is the outer HTML wrapper. Since [Propeller Helpers](/documentation/view/propeller-helpers) and [Handlebars](/documentation/view/handlebarsjs) are not available on this level, this should be for static content around the page such as headers, navigation bars, or footers that should look the same across different pages in the site.

Templates can also be used by multiple pages or collections that have the same markup but different content. This is where [Propeller Helpers](/documentation/view/propeller-helpers) and [Handlebars](/documentation/view/handlebarsjs) can be used to render the content that is filled out in Admin.

For both the layout and template, you can either choose existing HTML files within the dropdown, or create new ones. Any files that are listed in the dropdowns will be automatically created in your project's `/compartments/layouts/` and `/compartments/templates/` directories when executing `airship land` at the command line.

For more information, check out the documentation on the following topics: [Layouts](/documentation/view/layouts), [Page Templates](/documentation/view/page-templates), [Airship CLI Commands](/documentation/view/airship-cli-commands).


### Page Specific Fields
The following properties and fields are only available on Pages.

#### Permalink
The permalink is the identifier for page following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. By default, it is equivalent to the page title with any invalid characters parsed out, but can also be modified when creating or editing the page.


### Datafields  
The Page Fields section includes a variety of datafields to use in order to start creating page content. There are four fields that are created by default and cannot be modified: ID, Created At, Updated At, and Title.

When adding new fields, each field requires a Title, Variable Name, and Type. The order of these datafields can be changed by dragging each field into the proper position.

The Title is the identifier for the field. When editing the Page, each field will have this identifier directly above the field input.

The Variable Name is the same as the Title, but _only_ contains lowercase letters, numbers, dashes, and underscores. The variable name is not editable, and is the identifier used when rendering the content from each field when using [Propeller Helpers](/documentation/view/propeller-helpers).

The Type of the field is optional and varies from text inputs to lists of images.

For more information and example usages, see the documentation on [Datafields](/documentation/view/datafields).


## Modify Page
In order to change the title, permalink, layout, template, or fields on a page, you must Modify the page. To change field content, see the [Edit Page](/documentation/view/pages#user-content-edit-page) section for more information.

To modify a page, navigate to `Pages` within Admin from the sidebar at the left, and click the wrench tool icon on the page you would like to modify. The `Modify` tab at the top right should be the active tab, and the page title at the top should now include the text `(Modify)`. This page can also be reached from the Edit Page tab by clicking the Modify tab.

Be sure to click the `Modify Page` button at either the top or bottom of the page after making all desired changes.



## Edit Page
To edit the content entered for any page field, navigate to `Pages` within Admin from the sidebar at the left, and click the pencil icon on the page you would like to edit.

The `Edit Page` tab at the top right should be the active tab, and the page title at the top should now be preceded by the text `Edit Page:`. This page can also be reached from the Modify Page tab by clicking the Edit Page tab.

To save your changes, use either the `Save` button, or the `Save & Close` button. Use `Save` if you would just like to quickly save your changes without leaving the Edit Page. Use the `Save & Close` button to save and return to the `Pages` page. 


## Delete Page
To delete a page, navigate to the Modify page for the page you would like to delete.

At the bottom of the page, click the `Delete Page` link. When prompted, click `Confirm Delete`.

For more information about navigating to the Modify Page, see the [Modify Page section](/documentation/view/pages#user-content-modify-page).
