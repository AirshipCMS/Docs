The following examples show how to render each property from aerostat_collection:

### `aerostat_collection.id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
<p>{{aerostat_collection.id}}</p>
```

Example Output:
```
<p>305</p>
```


### `aerostat_collection.site_id`
This is the ID of the website given by Airship CMS.

Example Markup:
```
<p>{{aerostat_collection.site_id}}</p>
```

Example Output:
```
<p>62</p>
```


### `aerostat_collection.title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.title}}</p>
```

Example Output:
```
<p>Mammals</p>
```


### `aerostat_collection.name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.name}}</p>
```

Example Output:
```
<p>mammals</p>
```


### `aerostat_collection.public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{aerostat_collection.public_path}}</p>
```

Example Output:
```
<p>mammals</p>
```


### `aerostat_collection.has_public_make`
This shows whether or not public make is enabled for the current collection. The public make setting can be enabled/disabled in the Modify panel in Admin.

Public make must be enabled for user submissions, such as creating new Contact items within a Sign Up collection via sign up form. 

Example Markup:
```
<p>{{aerostat_collection.has_public_make}}</p>
```

Example Output:
```
<p>false</p>
```


### `aerostat_collection.has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

### `aerostat_collection.has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

### `aerostat_collection.has_comments`
Example Markup:
```
<p>{{aerostat_collection.has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

### `aerostat_collection.has_publish_date`
Example Markup:
```
<p>{{aerostat_collection.has_publish_date}}</p>
```

Example Output:


### `aerostat_collection.has_products`
This shows whether or not the collection is a product collection and contains any products.

Example Markup:
```
<p>{{aerostat_collection.has_products}}</p>
```

Example Output:
```
<p>false</p>
```


### `aerostat_collection.show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```


### `aerostat_collection.layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{aerostat_collection.layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

### `aerostat_collection.primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```


### `aerostat_collection.template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{aerostat_collection.template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```


### `aerostat_collection.created_at`
This is the timestamp for when the item was created. 

Example Markup:
```
<p>{{format_date aerostat_collection.created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


### `aerostat_collection.updated_at`
This is the timestamp for when the item was last updated.

Exapmle Markup:
```
<p>{{format_date aerostat_collection.updated_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


### `aerostat_collection.has_plans`
Example Markup:
```
<p>{{aerostat_collection.has_plans}}</p>
```

Example Output:
```
<p>false</p>
```
