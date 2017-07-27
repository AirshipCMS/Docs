The `params` property is for pagination. The following data is available from the show.html page of a collection:
```
page
limit
offset
sort
order
```

For more info about how to use these for pagination, see the documentation on the [create_page_query](/documentation/view/propeller-helpers#user-content-create_page_query) helper.

Example markup using the `{{create_page_query}}` helper with fields from `params` to create a link with a query string for pagination:
```
<li><a href="{{create_page_query page='1' sort=params.sort order=params.order limit='15'}}">Mammals</a></li>
```

Example Output HTML:
```
<li><a href="?page=1&amp;limit=15&amp;sort=id&amp;order=asc">Mammals</a></li>
```

Example Output Query String:
```
/mammals?page=1&limit=15&sort=id&order=asc
```
