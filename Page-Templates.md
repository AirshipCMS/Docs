# Page Templates
Your page template should be located in...
The filename should match what is set in the Modify section in the admin...

---

## Page Properties:
The following properties can be rendered on a Page Template:


#### Property: `name`
This is the name of the page. Example Markup:
```
<p>{{name}}</p>
```
Example Output:  
**About Airship**  


#### Property: `permalink`
The permalink is the identifier for page following `/` in the url. The permalink contains only lowercase letters, numbers, underscores, and dashes. Example Markup:
```
<p>{{permalink}}</a>
```

Example Output:  
**about**


#### Property: `slug`
The slug is the entire path to the page permalink including the `/` following the domain. Example Markup:
```
<p>{{slug}}</a>
```

Example Output:  
**/about**

---

## What cannot be rendered on a page template?
Only page properties render on pages with propellers. Data from other pages or collections will not render with propellers, unless you relate them to the page with a "related datafield."

If you want to render content outside of the page, you need to do an api call and render with a script.
