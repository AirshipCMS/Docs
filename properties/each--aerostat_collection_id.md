This is the id of the item's collection.

Example Markup:
```
{{#each items}}
<p>{{aerostat_collection_id}}</p>
{{/each}}
```

Because the aerostat collection id is the same for every item in the collection, we expect the same value for each item. Example Output:
```
<p>305</p>
<p>305</p>
```
