### `aerostat_collection.id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
{{#each items}}
<p>{{aerostat_collection.id}}</p>
{{/each}}
```

Example Output:
```
<p>305</p>
<p>305</p>
```

### `aerostat_collection.public_path`
This is the identifier for the item's collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
{{#each items}}
<p>{{aerostat_collection.public_path}}</p>
{{/each}}
```

Example Output:
```
<p>mammals</p>
<p>mammals</p>
```
