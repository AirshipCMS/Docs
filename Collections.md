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

## Create a New Collection (Superadmins Only)
To create a new collection, click the New Collection button at the top right of the Collections section in Airship CMS.

### Collection Setup

#### Title
This is the identifier for the collection.

#### Public Path
The Public Path is the identifier for collection following / in the url. The Public Path contains only lowercase letters, numbers, underscores, and dashes. By default, the Public Path is generated from the Title except that it contains only lowercase letters, numbers, underscores, and dashes. You may also modify the Public Path to change the default value.

#### Collection URLs
For collections utilizing the `show.html` layout, a single item in the collection will render at `http://subdomain.airshipcms.io/public_path/view/permalink`.

For collections utilizing the `categories.html` layout, collection categories will render at `http://subdomain.airshipcms.io/public_path/categories`.

For collections utilizing the `category.html` layout, items in a category will render at `http://subdomain.airshipcms.io/public_path/categories/category-permalink`.

Example: If you choose the title `Event Services` for a collection, the public path will autofill to be `event-services`. The index page of your collection would be accessible at `yourwebsitename.com/event-services`, categories will render at `yourwebsitename.com/event-services/categories`, a list of posts within a category will render at `yourwebsitename.com/event-services/categories/category-permalink`, and a single post will render at `yourwebsitename.com/event-services/view/permalink`.

#### Name
The Name is what a single item in the collection is called. By default, the name is generated from the Title, except you might want to edit it to be more human-readible.

Example: If you choose the title `Event Services`, the Name will autofill to be `event_services`, though you may want to rename it to be `service`. To see if you have set a good Name, check if it makes sense in the sentence: "A single item in the collection **Event Services** is a(n) **service**."

### Collection Rendering
The values set for Layouts and Templates correspond to the html files that are used to render the page.

#### Layout
A layout is the outer HTML wrapper of content on an Airship site. The layout usually contains static content that is repeated across many pages and collections of a site (such as headers, navigation bars, or footers). A single layout can be used for multiple pages and collections on an Airship site. For more information, see [Layouts](https://airshipcms.io/documentation/view/layouts).

Choose an existing layout, or create a new one.

When you create a new layout, it will automatically be generated on the Airship Server. When you execute the command `airship land` the file will download to the `/compartments/layouts/` directory.

#### Template Directory
A template directory contains a set of four templates specific to the collection: `index.html`, `show.html`, `categories.html`, and `category.html`. Each template displays properties and fields for the collection. For more information, see [Collection Templates](https://airshipcms.io/documentation/view/collection-templates).

Choose an existing template directory, or create a new one.

When you create a new template directory, it will automatically be generated on the Airship Server. When you execute the command `airship land` the directory and four templates will download to the `/compartments/templates/` directory.

### Collection Settings

#### Will this Collection have Categories?
This turns on Categories for the collection. Admins will be able to add/edit/delete categories and sort items in the collection into categories.

#### Will this Collection have Tags?
This turns on Tags for the collection. Admins will be able to add and delete tags for items in the collection.

#### Is the Permalink field editable by Admin Users?
When enabled, this shows the Permalink field in the Edit Content view of an item in the collection. By default, this field is enabled.

#### Will this Collection allow user submissions?
When public make is enabled, anonymous users can create POST requests to the collection.

### Post Fields
The Post Fields section displays data specific to the collection. 

#### Default Post Properties
There are three properties that are created by default and cannot be removed: `ID`, `Created At`, and `Updated At`. If Categories are enabled for the collection `Categories` will show in the list. If Tags are enabled for the collection `Tags` will show in the list. 

#### Custom Post Fields
When you add custom fields, each field requires a `Title`, `Variable Name`, and `Type`. The order of these datafields can be changed by dragging and dropping each field into the desired order.

These fields will contain all of the data that will be rendered on your site using Airship Propellers. You can create as many fields as needed as long as each variable name is unique.

Fields can be reordered by clicking and dragging the field into the desired position within the post fields list.

#### Title
The `Title` is the identifier for the field. When editing the content for a post, this displays as the label directly above the field input.

You can edit the field title by clicking the grey-pencil at the right of the field. 

#### Variable Name
By default, the `Variable Name` is the title in lowercase, with spaces converted to underscores. You may customize each variable name, however, keep in mind that having consistency between the title and variable name makes it easier to remember what value to use when rendering data with Propellers. Once set, the variable name is not editable.

#### Type
The `Type` of the field sets what content fields display in the CMS. Once set, the variable type is not editable.

For more information on datafields and example uses, see the documentation on [Datafields](https://airshipcms.io/documentation/view/datafields).

### Primary Label
The only purpose of the `Primary Label` is to identify what field will be set as the "main field" in the list view of items in the CMS. Primary Label can be set to `ID`, `Created At`, `Updated At`, `Permalink`, or any field from the Post Fields that is Type:Text.

---

## Modify a Collection (Superadmins Only)
To change properties and fields for a page, click the [ICON] Modify icon of the page you want to modify. Make changes to the page fields and properties and click the Modify Collection button.

---

## Delete a Collection (Superadmins Only)
To change properties and fields for a page, click the [ICON] Modify icon of the page you want to delete. At the bottom of the page, click the `Delete Collection` link. When prompted, click `Confirm Delete`.

When deleting a collection, **all** items within the collection will also be deleted. If any of the items are being referenced by a [related aerostats field](https://airshipcms.io/documentation/view/datafields#user-content-related-items), they will be deleted as well.

---

## Collection Items
An item in a collection is sometimes referred to as a "post", or the Airship term for a item is an "aerostat". For more information on item properties, see the [Collection Item Properties](https://airshipcms.io/documentation/view/collection-item-properties) Docs.

### View all Collection Items (Admins & Superadmins)
To view all of the items within the collection, navigate to the Admin panel, then click the Collection link on the sidebar at the left then click the [ICON] List All icon for the collection.

### Create an Item (Admins & Superadmins)
To create an item, navigate to the [ICON] List All view of the collection, then click `New Item` at the top right.
Fill in the desired fields, then click `Create`.

In order for each item to be publicly visible on the site, the item must have a Publish Date set to a past or current date. Set a publish date by toggling the `Draft Item` at the right when creating/editing the item, and then choose a date for when it should be published.

### Edit an Item (Admins & Superadmins)
To edit an item, navigate to the [ICON] List All view of the collection, then click the [ICON] Edit Content icon for the item.
Edit the desired files, then click either the `Save` button, or the `Save & Close` button. 

### Delete an Item (Admins & Superadmins)
To delete an item, navigate to the [ICON] List All view of the collection, then click the [ICON] Edit Content icon for the item. At the bottom left of the page, then click the `Delete` button, then Confirm to delete.

---

## Collection Categories
Items in a collection can be organized into Categories. See the [Categories](https://airshipcms.io/documentation/view/categories) Docs for more information.

---

## Display Order of Collection Items
In the Admin, items in a collection can be displayed by their Publish Date, Created Date, Permalink or Sort Order.

### Set the CMS display order of Collection Items (Admins & Superadmins)
To change the sort order of collection items, click the `Sort Order` filter, then click the [ICON] Edit Icon that appears within the Sort Order filter. Drag and drop items into the desired order, then click Save Sort Order.

### Set the published site display order of Collection Items (Superadmins Only)
Setting the sort order in the Admin adds a "sorting_position" value to items. However, the display order of items on a published site is determined by how the developer chooses to render items in a collection. See [Collection Templates](https://airshipcms.io/documentation/view/collection-templates) for more information on displaying lists of items in a collection.
