# Collections
In Airship, a collection is **a group of items, where each item in the group shares the same structure of data**.

In the context of a website, an Airship Collection could be a Blog, a Collection of Photo Galleries, or a Directory of Team Members.

[image]

An Airship Collection could function as a Form, where every form submission is an item in the collection. The only difference between a public collection such as a blog and a contact form collection, is whether or not posts can be submitted by public visitors and whether or not posts are published.

[image]

Even Products are a Collection (a special collection that we call a "Product Collection") since products can be grouped by their data structure.

[image]

In the context of a web application, collections can be used to manage and display user generated content.

[image]

The flexibility of Airship Collections lets you build a very complex project architecture based on fairly simple blocks of data.

---

## View All Collections
To view all of the pages within the site, navigate to the Admin panel, then click the Collections link on the sidebar at the left.

## Create a New Collection (superadmin)
To create a new collection, click the New Collection button at the top right of the Collections section in Airship CMS.

### Collection Setup

#### Title
This is the identifier for the collection.

#### Public Path
The Public Path is the identifier for collection following / in the url. The Public Path contains only lowercase letters, numbers, underscores, and dashes. By default, the Public Path is generated from the Title except that it contains only lowercase letters, numbers, underscores, and dashes. You may also modify the Public Path to change the default value.

Example: If you choose the title `Event Services`, the public path will autofill to be `event-services`. The index page of your collection would be accessible at `/yourwebsitename.com/event-services`.

#### Name
The Name is what a single item in the collection is called. By default, the name is generated from the Title, except you might want to edit it to be more human-readible.

Example: If you choose the title `Event Services`, the Name will autofill to be `event_services`, though you may want to rename it to be `service`. To see if you have set a good Name, check if it makes sense in the sentence: "A single item in the collection **Event Services** is a(n) **service**."

#### Collection Rendering
The values set for Layouts and Templates correspond to the html files that are used to render the page.

#### Layout
A layout is the outer HTML wrapper of content on an Airship site. The layout usually contains static content that is repeated across many pages and collections of a site (such as headers, navigation bars, or footers). A single layout can be used for multiple pages and collections on an Airship site. For more information, see [Layouts](/documentation/view/layouts).

Choose an existing layout, or create a new one.

When you create a new layout, it will automatically be generated on the Airship Server. When you execute the command `airship land` the file will download to the `/compartments/layouts/` directory.

#### Template Directory
A template directory contains a set of four templates specific to the collection: `index.html`, `show.html`, `categories.html`, and `category.html`. Each template displays properties and fields for the collection. For more information, see [Collection Templates](/documentation/view/collection-templates).

Choose an existing template directory, or create a new one.

When you create a new template directory, it will automatically be generated on the Airship Server. When you execute the command `airship land` the directory and four templates will download to the `/compartments/templates/` directory.

#### Collection Settings
The first two are whether or not the collection will have Categories or Tags. If categories are enabled, each item can be put into smaller groups, such as categorizing blogs under various topics. When categories are enabled, the categories.html and category.html page can then be used for category specific views on the site. If tags are enabled, each item can then be tagged with keywords, which can be used for filtering or other indexing purposes. Each item can have multiple categories and tags.

The third option, `Is the Permalink field editable by Admin Users?`, is the option to enable or disable whether or not Admin users can customize each item's permalink.

The fourth option, `Will this Collection allow user submissions?`, is the option to enable or disable Public Make. When public make is enabled, items or posts can be created from the site rather than just in Admin, such as through contact forms or other methods using POST requests.

#### Post Fields

##### Categories
Categories are used to create other, more specific, groups within each collection. When categories are enabled, the use of the categories.html and category.html pages can be used to render different category specific views in your site.

For more information, see the [Categories](/documentation/view/categories) documentation.

##### Tags
Tags are used to attach keywords to each aerostat, which can then be used for either other grouping or indexing purposes.

For more information, see the [Tags](/documentation/view/tags) documentation.


### Datafields
The Post Fields section includes a variety of datafields to use in order to start creating page content. There are four fields that are created by default and cannot be modified: ID, Created At, Updated At, and Title.

When adding new fields, each field requires a Title, Variable Name, and Type. The order of these datafields can be changed by dragging each field into the proper position.

The Title is the identifier for the field. When editing the Page, each field will have this identifier directly above the field input.

The Variable Name is the same as the Title, but _only_ contains lowercase letters, numbers, dashes, and underscores. The variable name is not editable, and is the identifier used when rendering the content from each field when using [Propeller Helpers](/documentation/view/propeller-helpers).

The Type of the field is optional and varies from text inputs to lists of images.

For more information and example usages, see the documentation on [Datafields](/documentation/view/datafields).

### Aerostats
Aerostats are items in each collection.

See the [Collection Item Properties](/documentation/view/collection-item-properties) documentation for more information.


## Modify a Collection
In order to change the title, public path, layout, template, settings or fields on a collection, you must Modify the collection. To change the content for an item, see the [Edit an Aerostat](/documentation/view/collections#user-content-edit-an-aerostat) section for more information.

To modify a collection, navigate to `Collections` within Admin from the sidebar at the left, and click the wrench tool icon on the collection you would like to modify. The Modify tab at the top right should be the active tab, and the collection title at the top should now include the text `(Modify)`.

Be sure to click the `Modify Collection` button at either the top or bottom of the page after making all desired changes.


## Create an Aerostat
To create an Aerostat, navigate to the List All view of the collection in which the new Aerostat should belong to, then click `New Item` at the top right. To get to the List All view of the collection, first navigate to the `Collections` page in Admin from the sidebar at the left, then click the list icon on the desired collection. The active tab at the top right should say `List All`.

Fill in the desired fields, categories, or tags, then click `Create` at either the top or bottom right of the page.

In order for each item to be publicly available on the site, the item must have a Publish Date set to one that is not in the future. Set a publish date by toggling the `Draft Item` at the right when creating/editing the item, and then choose a date for when it should be published.

See the [Collection Item Properties](/documentation/view/collection-item-properties) documentation for more information.


## Edit an Aerostat
To edit an Aerostat, navigate to the List All view of the collection in which the Aerostat belongs to, then click the pencil icon at the far right of the item. To get to the List View of the collection, first navigate to the `Collections` page in Admin from the sidebar at the left, then click the list icon on the desired collection. The active tab at the top right should say `List All`.

To save your changes, use either the `Save` button, or the `Save & Close` button. Use `Save` if you would just like to quickly save your changes without leaving the Edit page. Use the `Save & Close` button to save and return to the List All view of the collection.


## Delete Collection
When deleting a collection, **all** aerostats within the collection will also be deleted. If any of the aerostats are being referenced by a [related aerostats field](/documentation/view/datafields#user-content-related-items), they will be deleted as well.

To delete a collection, navigate to the Modify view for the collection you would like to delete.

At the bottom of the page, click the `Delete Collection` link. When prompted, click `Confirm Delete`.

For more information about navigating to the Modify view, see the [Modify a Collection](/documentation/view/collections#user-content-modify-a-collection) section.
