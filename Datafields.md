# Datafields
Content entered in the Admin panel can be rendered using Propellers.

Propellers follow syntax similar to: `{{variable_name}}`.

For fields that contain HTML, use triple braces: `{{{variable_name}}}`.

Some fields that include multiple inputs for content require the `{{#each}}` helper. When rendering `{{{help}}}`, these fields are notated with `[list]` next to the field's variable name, followed by a bulleted list of fields to access. Some examples of these fields are [image](/documentation/view/datafields#user-content-image), [link](/documentation/view/datafields#user-content-link), or [related aerostats](/documentation/view/datafields#user-content-related-items).

`List of` fields also require the `{{#each}}` helper. These fields, e.g. [list of images](/documentation/view/datafields#user-content-list-of-images) or [list of links](/documentation/view/datafields#user-content-list-of-links), are arrays of items. The order of which these items are rendered can be controlled either in Admin, or using the [#sort_list](/documentation/view/propeller-helpers#user-content-sort_list) propeller. The `{{#sort_list}}` propeller takes precedence over the order determined in Admin.


The following field types are available:

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
