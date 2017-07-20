Example markup using a multiselect field and:
- variable name: `things`
- multiselect options: `Thing 1`, `Thing 2`, and `Thing 3`
- The admin has set the value to `Thing 2` and `Thing 3`

```
<div class="all-the-things">
  {{#each fields.things}}
  <p>{{this}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="all-the-things">
  <p>Thing 2</p>
  <p>Thing 3</p>
</div>
```

Alternatively, the values for a multiselect field can also be rendered as a comma separated list for simplicity. Example:
```
<p>{{fields.thing}}</p>
```
