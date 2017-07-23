This is the timestamp of when an item was created. It can be formatted using the `{{format_date}}` helper.

Example Markup:
```
{{#each items}}
<p>{{format_date created_at "d" "us"}}</p>
{{/each}}
```

Example Output:  
```
<p>5/13/2017</p>
<p>5/17/2017</p>
<p>5/19/2017</p>
```

---
/documentation/view/propeller-helpers#user-content-format_date
