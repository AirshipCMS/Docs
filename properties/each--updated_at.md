This is the timestamp of when the current item was last updated. It can be formatted using the `{{format_date}}` helper.

Example Markup:
```
{{#each items}}
<p>{{format_date updated_at "u" "us"}}</p>
{{/each}}
```

Example Output:
```
<p>2017-05-24 06:15:52Z</p>
<p>2017-05-30 06:22:59Z</p>
```

---
/documentation/view/propeller-helpers#user-content-format_date
