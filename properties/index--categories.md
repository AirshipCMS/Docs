To use these properties, categories must be enabled in the Admin panel for the collection. The following examples show how to render the available categories properties for each item:

### `id`
This is the ID of the category.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>320</p>
<p>319</p>
```

### `title`
This is the category name.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{title}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Common</p>
<p>Fluffy</p>
```

### `permalink`
The permalink is the identifier for the category following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{permalink}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>common</p>
<p>fluffy</p>
```


### `created_at`
This is the timestamp of when the category was created.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{format_date created_at "r" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Wed, 17 May 2017 04:02:26 GMT</p>
<p>Wed, 17 May 2017 04:02:10 GMT</p>
```

### `updated_at`
This is the timestamp of when the category was last updated.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-30 06:22:59Z</p>
```

### `sorting_position`
This is the value of the category's sorting position.

Example Markup:
```
{{#each items}}{{#each categories}}
<p>{{sorting_position}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>1</p>
<p>0</p>
```
