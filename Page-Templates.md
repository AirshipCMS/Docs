# Page Templates

## Template filenames
Your page template should be located in...
The filename should match what is set in the Modify section...

## Page Built-in Server-side Rendering with Propellers:
- fields content for the current page.
- top-level properties & fields content from related posts connected to this page.

The following properties can be rendered on a Page Template:

### `name`
The name of the page.

Example Markup:
```
<p>{{name}}</p>
```

Example Output:
**About Airship**

## No Server-side Rendering:
If you want to render these items, you need to do an api call and render with a script.
- fields and content from other pages or collections.
