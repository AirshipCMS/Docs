Example markup using a select field and:
- variable name: `animal_kingdom`
- select options: `Plants`, `Animals`, and `Fungi`
- The admin has set the value to `Animals`

```
<p>Animal Kingdom: {{fields.animal_kingdom}}</p>
```

Example Output:
```
<p>Animal Kingdom: Animals</p>
```

Another Example, where you can use a select field as an admin setting for CSS:
- variable name: `theme`
- select options: `red`, `green`, and `blue`
- The admin has set the value to `red`

```
<h1 class="{{fields.theme}}-theme">Welcome</h1>
```

Example Output:
```
<h1 class="red-theme">Welcome</h1>
```
