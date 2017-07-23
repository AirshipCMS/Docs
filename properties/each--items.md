Each item in a collection can be accessed through the `items` property. The markup `{{items}}` alone will not render anything. An `{{#each items}}{{/each}}` wrapper is required to render the content within `items`. Alternatively, the `{{#sort_list items}}` helper may also be used in place of `{{#each items}}`.

When using propeller helpers, outside properties may still be accessed by using the following syntax: `{{../variable_name}}`.

Example rendering the ids of all items:
```
{{#each items}}
<p>{{id}}</p>
{{/each}}
```
