This represents the sorting position of the item.
The item's sorting position can be modified by editing the sort order in the Airship CMS admin panel.

Example where the sorting position property is used by the `{{#sort_list}}` helper to display items in the order they are ordered in the Airship CMS admin panel:
```
{{#sort_list items sort="sorting_position" order="asc"}}
<p class="sorting-position-{{sorting_position}}">{{permalink}}</p>
{{/sort_list}}
```

Example Output:
```
<p class="sorting-position-1">cat</p>
<p class="sorting-position-2">dog</p>
<p class="sorting-position-3">fish</p>
```
Example where the sorting position property is listed, within an `{{#each items}}` helper:
```
{{#each items}}
<p>{{sorting_position}}</p>
{{/each}}
```

Example Output:
```
<p>1</p>
<p>2</p>
<p>3</p>
```
