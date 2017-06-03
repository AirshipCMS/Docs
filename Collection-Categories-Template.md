# Collection `categories.html` Template:
The following properties and fields are available on the categories.html template:

## Property: `id`
This is the id of the item's collection given by Airship CMS.

Example Markup:
```
<p>{{id}}</p>
```

Example Output:
```
<p>305</p>
```


## Property: `site_id`
This is the ID of the website given by Airship CMS.

Example Markup:
```
<p>{{site_id}}</p>
```

Example Output:
```
<p>62</p>
```


## Property: `title`
This is the title of the collection. The title is set when creating each collection, and can be edited at any time in the Modify panel in Admin.

Example Markup:
```
<p>{{title}}</p>
```

Example Output:
```
<p>Mammals</p>
```


## Property: `name`
This is the identifier used to refer to each item in the collection. By default, it is the same as the collection's title. It can be found and edited in the Modify panel in Admin.

Example Markup:
```
<p>{{name}}</p>
```

Example Output:
```
<p>mammals</p>
```


## Property: `public_path`
The public path is the identifier for collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{public_path}}</p>
```

Example Output:
```
<p>mammals</p>
```


## Property: `has_public_make`
This shows whether or not public make is enabled for the current collection. The public make setting can be enabled/disabled in the Modify panel in Admin.

Public make must be enabled for user submissions, such as creating new Contact items within a Sign Up collection via sign up form. 

Example Markup:
```
<p>{{has_public_make}}</p>
```

Example Output:
```
<p>false</p>
```


## Property: `has_categories`
This shows whether or not categories are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{has_categories}}</p>
```

Example Output:
```
<p>true</p>
```

## Property: `has_tags`
This shows whether or not tags are enabled for the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{has_tags}}</p>
```

Example Output:
```
<p>true</p>
```

## Property: `has_comments`
Example Markup:
```
<p>{{has_comments}}</p>
```

Example Output:
```
<p>false</p>
```

## Property: `has_publish_date`
Example Markup:
```
<p>{{has_publish_date}}</p>
```

Example Output:


## Property: `has_products`
This shows whether or not the collection is a product collection and has products.

Example Markup:
```
<p>{{has_products}}</p>
```

Example Output:
```
<p>false</p>
```


## Property: `show_permalink`
This shows whether or not user's are allowed to edit the permalink for each item in the current collection. This setting can be enabled/disabled in the Modify panel in Admin.

Example Markup:
```
<p>{{show_permalink}}</p>
```

Example Output:
```
<p>true</p>
```


## Property: `cat_fields`
This property holds information about the collection's category fields.

The following are examples of how to access the cat_fields properties:

### Property: `num_options`
This represents the amount of options that are available for the field.

Example Markup:
```
{{#each cat_fields}}
<p>{{num_options}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
```


### Property: `type`
This represents the datafield type.

Example Markup:
```
{{#each cat_fields}}
<p>{{type}}</p>
{{/each}}
```

Example Output:
```
<p>number</p>
```


### Property: `options`

Example Markup:

Example Output:


### Property: `title`
This represents the category field name.

Example Markup:
```
{{#each cat_fields}}
<p>{{title}}</p>
{{/each}}
```

Example Output:
```
<p>Population Size</p>
```


### Property: `variable_name`
This represents the variable name of the category field.

Example Markup:
```
{{#each cat_fields}}
<p>{{variable_name}}</p>
{{/each}}
```

Example Output:
```
<p>population_size</p>
```


### Property: `sorting_position`
This represents the sorting position of the field, beginning from 0.

Example Markup:
```
{{#each cat_fields}}
<p>{{sorting_position}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
```


## Property: `variations`
Example Markup:

Example Output:


## Property: `layout`
This shows which layout is being used to render the current collection. This can be set within the Modify panel in Admin. 

Example Markup:
```
<p>{{layout}}</p>
```

Example Output:
```
<p>mammals.html</p>
```

## Property: `primary_label`
This shows which field is being used as the primary identifier when listing each item in a collection. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{primary_label}}</p>
```

Example Output:
```
<p>Name</p>
```


## Property: `template_directory`
This shows the name of the template directory being used for the current collection, and which holds the collection's index, show, categories, and/or category html files. The directory name in the project structure must exactly match this value. This can be set within the Modify panel in Admin.

Example Markup:
```
<p>{{template_directory}}</p>
```

Example Output:
```
<p>mammals</p>
```


## Property: `created_at`
This is the timestamp of when the category was created. The timestamp can be formatted using the [format_date helper](Propeller-Helpers.md#format_date).

Example Markup:
```
<p>{{format_date created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


## Property: `updated_at`
This is the timestamp of when the category was last updated. The timestamp can be formatted using the [format_date helper](Propeller-Helpers.md#format_date).

Exapmle Markup:
```
<p>{{format_date updated_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


## Property: `has_plans`
Example Markup:
```
<p>{{collection.has_plans}}</p>
```

Example Output:
```
<p>false</p>
```


## Property: `categories`
To use these properties, categories must be enabled in the Admin panel for the collection. The following examples show how to render the available categories properties for each item:

### Property: `id`
This is the ID of the category.

Example Markup:
```
{{#each categories}}
<p>{{id}}</p>
{{/each}}
```

Example Output:
```
<p>319</p>
```

### Property: `title`
This is the category name.

Example Markup:
```
{{#each categories}}
<p>{{title}}</p>
{{/each}}
```

Example Output:
```
<p>Fluffy</p>
```

### Property: `permalink`
The permalink is the identifier for the category following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
{{#each categories}}
<p>{{permalink}}</p>
{{/each}}
```

Example Output:
```
<p>fluffy</p>
```


### Property: `aerostat_collection_id`
This is the ID of the collection given by Airship CMS.

Example Markup:
```
{{#each categories}}
<p>{{aerostat_collection_id}}</p>
{{/each}}
```

Example Output:
```
<p>305</p>
```

### Property: `created_at`
This is the timestamp of when the category was created.

Example Markup:
```
{{#each categories}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```

### Property: `updated_at`
This is the timestamp of when the category was last updated.

Example Markup:
```
{{#each categories}}
<p>{{format_date updated_at "D" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>Wednesday, May 31, 2017</p>
```


### Property: `sorting_position`
This is the value of the category's sorting position.

Example Markup:
```
{{#each categories}}
<p>{{sorting_position}}</p>
{{/each}}
```

Example Output:
```
<p>0</p>
```
