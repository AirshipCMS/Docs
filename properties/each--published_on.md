This is the timestamp of when an item was published. The publish date can be set in the Admin panel. It can be formatted using the `{{format_date}}` helper.

Example markup:
```
{{#each items}}
<p>{{format_date published_on "r" "us"}}</p>
{{/each}}
```

Output:
```
<p>Sat, 20 May 2017 00:00:00 GMT</p>
<p>Mon, 22 May 2017 00:00:00 GMT</p>
```

---
/documentation/view/propeller-helpers#user-content-format_date
