The `params` property is for pagination. It contains the following data:
```
page
limit
offset
sort
order
total_count
page_count
next_offset
prev_offset
next_page
prev_page
fetch_first
fetch_last
fetch_prev
fetch_next
fetch_first_offset
fetch_last_offset
fetch_prev_offset
fetch_next_offset
```

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

---
create_page_query helper
