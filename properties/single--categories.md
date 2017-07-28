## Categories
When categories are enabled on [collections](/documentation/view/collections), this property holds information such as `title` or `permalink`, that can be used with propellers for rendering.

To see what is accessible on `categories`, add `{{{help}}}` to the collection template page to see the list of properties and fields. See the [collection template documentation](/documentation/view/collection-templates) for more information and examples.

Example Markup rendering the categories permalink property:
```
{{#each categories}}
<p>{{permalink}}</p>
{{/each}}
```

Example Output:
```
<p>new</p>
```
