# Collections
Collections are groups of things. In Airship CMS, you can create a collection for any group of things that your site might require such as blogs, provided services, or even to hold contact form submissions. Collections can also include categories or tags if enabled.


## Create a Collection
To create a new collection, navigate to Collections within Admin from the sidebar at the left, then click the `New Collection` button at the top right.

### Collection Setup
The first field to fill out is the `Title` under Collection Setup. This will be the identifier for this collection.

The `Refer to a single item in this collection as a(n)...` and `Public Path` fields will be entered as you fill out the Title field by default, though you can still edit them to the desired values. The Public Path contains only lowercase letters, numbers, dashes, or underscores. 

For example, if you choose the title `Event Services`, the Refer to field will then become `event_services`, and the public path will become `event-services` by default. The index page of your collection would be accessible at `/yourwebsitename.com/event-services`.

For more information about the different collection pages such as index, check out the [Collection Templates](/documentation/view/collection-templates) documentation.


### Collection Layout & Template Directory
Under this section, there are two dropdowns: Layout and Template Directory.

A single layout can be used for multiple template or template directories. The layout file is the outer HTML wrapper. Since [Propeller Helpers](/documentation/view/propeller-helpers) and [Handlebars](/documentation/view/handlebarsjs) are not available on this level, this should be for static content around the page such as headers, navigation bars, or footers that should look the same across different pages in the site.

Template Directories can also be used by multiple pages or collections that have the same markup but different content. This will be the name of the directory that holds the collection's HTML pages, such as index.html, show.html, categories.html, or category.html. These files are where [Propeller Helpers](/documentation/view/propeller-helpers) and [Handlebars](/documentation/view/handlebarsjs) can be used to render the content that is filled out in Admin for each item.

For both the layout and template directory, you can either choose existing options within the dropdown, or create new ones. Any files or directories that are listed in the dropdowns will be automatically created in your project's `/compartments/layouts/` and `/compartments/templates/` directories when executing `airship land` at the command line.

For more information, check out the documentation on the following topics: [Layouts](/documentation/view/layouts), [Collection Templates](/documentation/view/collection-templates), [Airship CLI Commands](/documentation/view/airship-cli-commands).


### Collection Settings
There are four options to enable or disable within the Collection Settings.

The first two are whether or not the collection will have Categories or Tags. If categories are enabled, each item can be put into smaller groups, such as categorizing blogs under various topics. When categories are enabled, the categories.html and category.html page can then be used for category specific views on the site. If tags are enabled, each item can then be tagged with keywords, which can be used for filtering or other indexing purposes. Each item can have multiple categories and tags.

The third option, `Is the Permalink field editable by Admin Users?`, is the option to enable or disable whether or not Admin users can customize each item's permalink.

The fourth option, `Will this Collection allow user submissions?`, is the option to enable or disable Public Make. When public make is enabled, items or posts can be created from the site rather than just in Admin, such as through contact forms or other methods using POST requests.


### Collection Specific Fields
The following are fields that are only available on Collections.

#### Categories
Categories are used to create other, more specific, groups within each collection. When categories are enabled, the use of the categories.html and category.html pages can be used to render different category specific views in your site.

For more information, see the [Categories](/documentation/view/categories) documentation.


#### Tags
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
