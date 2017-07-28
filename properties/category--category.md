This property holds information about the current category.

The following are examples of how to render each property and field on category:

### `category.id`
This is the ID of the category given by Airship CMS.

Example Markup:
```
<p>{{category.id}}</p>
```

Example Output:
```
<p>319</p>
```


### `category.title`
This is the title, or name, of the category.

Example Markup:
```
<p>{{category.title}}</p>
```

Example Output:
```
<p>Fluffy</p>
```


### `category.permalink`
The permalink is the identifier for the category following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
<p>{{category.permalink}}</p>
```

Example Output:
```
<p>fluffy</p>
```


### `category.fields`

For more information about rendering category fields, see the documentation for [Datafields](/documentation/view/datafields).


### `category.aerostat_collection_id`
This is the ID of the category's collection given by Airship CMS.

Example Markup:
```
<p>{{category.aerostat_collection_id}}</p>
```

Example Output:
```
<p>305</p>
```


### `category.created_at`
This is the timestamp of when the category was created.

Example Markup:
```
<p>{{format_date category.created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


### `category.updated_at`
This is a timestamp of when the category was last updated.

Example Markup:
```
<p>{{format_date category.updated_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


### `category.sorting_position`
This represents the sorting position of the category.

The sorting position of each category can be modified in Admin from the `Categories` tab by clicking `sort order` at the right, clicking on the pencil icon within the `sort order` button, then dragging the categories to the desired order.

Example Markup:
```
<p>{{category.sorting_position}}</p>
```

Example Output:
```
<p>0</p>
```
