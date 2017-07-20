The `textarea` field is useful for plain multi-line content, or text that is too long for the `text` field type.

Example markup using a textarea with the variable name `description`:
```
<p>{{fields.description}}</p>
```

Example Output:
```
<p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
```

It is also useful to use a `textarea` field to store html or complex content containing html markup or code snippets. If you use a `textarea` to store code snippets, be sure to use triple curly brackets to render the content:
```
<div class="code">
{{{fields.code}}}
</div>
```

Example Output:
```
<div class="code">
<style>
  body{
    background-color: red;
  }
</style>
</div>
```
