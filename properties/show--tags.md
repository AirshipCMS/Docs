To use these properties, tags must be enabled in the Admin panel for the collection. The following examples show how to render the available tag properties for each item:

### `id`
This is the ID of the tag given by Airship CMS.

Example Markup:
```
{{#each tags}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>572</p>
```

### `site_id`
This is the ID of the website that the tag belongs to.

Example Markup:
```
{{#each tags}}
<p>{{site_id}}</p>
{{/each}}
```

Example Output:
```
<p>62</p>
```

### `name`
This is the tag name.

Example Markup:
```
{{#each tags}}
<p>{{name}}</p>
{{/each}}
```

Example Output:
```
<p>carnivore</p>
```

### `created_at`
This is the timestamp of when the tag was created.

Example Markup:
```
{{#each tags}}
<p>{{format_date created_at "o" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-24T06:15:52.6890000+00:00</p>
```

### `updated_at`
This is the timestamp of when the tag was updated.

Example Markup:
```
{{#each tags}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
```
