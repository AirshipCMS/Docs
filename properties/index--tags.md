To use these properties, tags must be enabled in the Admin panel for the collection. The following examples show how to render the available tag properties for each item:

##### `id`
This is the ID of the tag given by Airship CMS.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>572</p>
<p>593</p>
```

##### `site_id`
This is the ID of the website that the tag belongs to.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{site_id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>62</p>
<p>62</p>
```

##### `name`
This is the tag name.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{name}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>carnivore</p>
<p>fluffy</p>
```

##### `created_at`
This is the timestamp of when the tag was created.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{format_date created_at "o" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24T06:15:52.6890000+00:00</p>
<p>2017-05-17T04:02:03.1730000+00:00</p>
```

##### `updated_at`
This is the timestamp of when the tag was updated.

Example Markup:
```
{{#each items}}{{#each tags}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-17 04:02:03Z</p>
```
