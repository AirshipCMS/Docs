Each item in the collection can be accessed through the items property. Because `items` is an array of items, the `{{#each items}}{{/each}}` wrapper is required to render the content. Alternatively, the [#sort_list](Propeller-Helpers.md#sort_list) helper may also be used.

When using propeller helpers, outside properties may still be accessed by using the following syntax: `{{../variable_name}}`. For example:
```
{{#each items}}
<p>{{../site_id}}</p>
{{/each}}
```
Within `{{#each items}}{{/each}}` item properties can be rendered.
