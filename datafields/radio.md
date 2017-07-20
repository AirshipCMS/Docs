Example markup using a radio field and:
- variable name `is_endangered`
- the radio options are `Yes` and `No`
- The admin has set the value to `No`

```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:
```
<p>Endangered: No</p>
```
