Example markup using a radio field and:
- variable name: `is_endangered`
- radio options: `Yes`, `No`
- The admin has set the value to `No`

```
<p>Endangered: {{fields.is_endangered}}</p>
```

Example Output:
```
<p>Endangered: No</p>
```

Another Example, where you can use a radio field as an admin setting for CSS:
- variable name: `theme`
- radio options: `red`, `green`, and `blue`
- The admin has set the value to `red`

```
<h1 class="{{fields.theme}}-theme">Welcome</h1>
```

Example Output:
```
<h1 class="red-theme">Welcome</h1>
```
