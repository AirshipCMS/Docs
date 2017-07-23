This represents the sorting position of the item.
The item's sorting position can be modified by editing the sort order in the Airship CMS admin panel.

Example Markup:
```
{{#sort_list items sort="sorting_position" order="asc"}}
<p>{{sorting_position}}</p>
{{/sort_list}}
```

Example Output:
```
<p>1</p>
<p>2</p>
<p>3</p>
```
