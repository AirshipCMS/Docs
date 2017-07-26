# Collection Item Properties
Properties available for Items in a Collection


## Categories
When categories are enabled on [collections](Collections.md), this property holds information such as `title` or `permalink`, that can be used with propellers for rendering.

To see what is accessible on `categories`, add `{{{help}}}` to the collection template page to see the list of properties and fields. See the [collection template documentation](Collection-Templates.md) for more information and examples.

Example Markup rendering the categories permalink property:
```
{{#each categories}}
<p>{{permalink}}</p>
{{/each}}
```

Example Output:
```
<p>new</p>
```


## Created At
This is a timestamp of when the item or page was created.

To render this property with a different time format, use the [format_date helper](Propeller-Helpers.md#format_date).

Example Markup:
```
<p>{{format_date created_at "D" "us"}}</p>
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
```


## Permalink
The permalink is the identifier for page following / in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes.

Example Markup:
```
<p>{{permalink}}</p>
```

Example Output:
```
<p>about</p>
```


## Product Title
In product collections, this is the title of each product. This property is created by default when creating product collections.

Example Markup:
```
<p>{{product_title}}</p>
```

Example Output:
```
<p>Food</p>
```


## Public Path
The public path is the identifier for the collection following / in the url. The public path contains only lowercase letters, numbers, underscores, and dashes. By default, it is the same as the title or name, and can be edited in the Admin panel at any time.

Example Markup:
```
<p>{{public_path}}</p>
```

```
<p>blogs</p>
```

## Published On
This is a timestamp of when the item was published.

To render this property with a different time format, use the [format_date helper](Propeller-Helpers.md#format_date).

Example Markup:
```
<p>{{format_date published_on "d" "us"}}</p>
```

Example Output:
```
<p>5/22/2017</p>
```

## Tags
When tags are enabled on [collections](Collections.md), this property holds information such as the tag name, that can be used with propellers for rendering.

To see what is accessible on `tags`, add `{{{help}}}` to the collection template page to see the list of properties and fields. See the [collection template documentation](Collection-Templates.md) for more information and examples.

Example Markup rendering the tag name on a collections index.html page:
```
{{#each items}}{{#each tags}}
<p>{{name}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Dogs</p>
<p>Cats</p>
```


## Title
This is the page title.

When rendering on a page, this property appears as `name` when rendering `{{{help}}}`.

Example Markup:
```
<p>{{name}}</p>
```

```
<p>About Airship</p>
```


## Updated At
This is a timestamp of when the item was published.

To render this property with a different time format, use the [format_date helper](Propeller-Helpers.md#format_date).

Example Markup:
```
<p>{{format_date updated_at "U" "us"}}</p>
```

Example Output:
```
<p>Tuesday, May 23, 2017 11:47:04 PM</p>
```

## Fields
