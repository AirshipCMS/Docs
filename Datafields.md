# Datafields
Custom Fields added to a Page, Collection, or Category can be rendered with datafield propellers. 

## Plain Rendering
Custom field content is typically rendered with double curly braces.
```
{{fields.variable_name}}
```

## HTML Rendering
For Custom Field content that contains HTML, use triple curly braces.
```
{{{fields.variable_name}}}
```

## Rendering Lists
Some custom fields require an `{{#each}}` helper for rendering. 
```
{{#each fields.variable_name}}
  ...
{{/each}}
```
When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of accessible properties:
- [image](https://airshipcms.io/documentation/view/datafields#user-content-image)
- [link](https://airshipcms.io/documentation/view/datafields#user-content-link)
- [list of links](https://airshipcms.io/documentation/view/datafields#user-content-list-of-links)
- [list of images](https://airshipcms.io/documentation/view/datafields#user-content-list-of-images)
- [multiselect](https://airshipcms.io/documentation/view/datafields#user-content-multiselect)

List of Images, List of Links, and Multiselect are arrays of items. The order of which these items are rendered can be controlled either in Admin, or by using the [#sort_list](https://airshipcms.io/documentation/view/propeller-helpers#user-content-sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.

## Related Items
While the `related aerostats` field is attached to a page, collection, or category as a datafield, it is rendered as a separate property rather than within the `fields` list.
- [related items](https://airshipcms.io/documentation/view/datafields#user-content-related-items)

## Datafields
- text
- textarea
- richtext area
- image
- link
- number
- radio
- select
- multiselect
- checkbox
- list of images
- list of links
- related aerostats
- date
