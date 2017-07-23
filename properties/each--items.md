# `{{#each items}}{{/each}}`

Each item in a collection can be accessed through the `items` property. The markup `{{items}}` alone will not render anything because it is simply a wrapper for the items it contains. It must be rendered as a wrapper `{{#each items}}{{/each}}` to display the content within `items`. Alternatively, the `{{#sort_list items}}` helper may also be used in place of `{{#each items}}`.

Example using `{{#each items}}`:
```
{{#each items}}
<p>{{id}}</p>
{{/each}}
```

Output:
```
<p>22</p>
<p>23</p>
<p>24</p>
```

Example using `{{#sort_list items}}`:
```
{{#sort_list items sort="permalink" order="asc"}}
<p>{{id}}</p>
{{/sort_list}}
```

Output:
```
<p>24</p>
<p>22</p>
<p>23</p>
```

---
/documentation/view/propeller-helpers#user-content-format_date
