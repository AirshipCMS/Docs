### `collection`
The following properties and fields are available on the index.html's `collection` property:

##### `id`
This is the collection's id.

Example Markup:
```
<p>{{collection.id}}</p>
```

Example Output:
```
<p>305</p>
```

##### `site_id`
This is the id of the website given by Airship CMS.

Example Markup:
```
<p>{{collection.site_id}}</p>
```

Example Output:
```
<p>62</p>
```

##### `title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.title}}</p>
```

Example Output:
```
<p>Mammals</p>
```

##### `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.name}}</p>
```

Example Output:
```
<p>mammals</p>
```

##### `public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{collection.public_path}}</p>
```

Example Output:
```
<p>mammals</p>
```

##### `has_public_make`
This shows whether or not public make is enabled for the current collection. The public make setting can be enabled/disabled in the Modify panel in Admin.

Public make must be enabled for user submissions, such as creating new Contact items within a Sign Up collection via sign up form. 

Example Markup:
```
<p>{{collection.has_public_make}}</p>
```

Example Output:
```
<p>false</p>
```

##### `has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

##### `has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

##### `has_comments`
Example Markup:
```
<p>{{collection.has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

##### `has_publish_date`
Example Markup:
```
<p>{{collection.has_publish_date}}</p>
```

Example Output:


##### `show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{collection.show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```

##### `layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{collection.layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

##### `primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```

##### `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{collection.template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```

##### `has_plans`
Example Markup:
```
<p>{{collection.has_plans}}</p>
```

Example Output:
```
<p>false</p>
```
