The permalink is the identifier for an item in a collection. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example markup on the `index.html` or `category.html` template:
```
{{#each items}}
<p>{{permalink}}</p>
{{/each
```

Output:
```
<p>dog</p>
<p>cat</p>
<p>fish</p>
```
