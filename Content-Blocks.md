# Content Blocks
A Content Block lets you store content that is specific to a template, and insert it into a partial or layout. This is especially useful when you want to add dynamic data from a template, and render it in the `<head>`, which is usually included in a layout. Normally, the layout would not have access to page template properties, however with a content block you can insert page data into the `<head>`.

To create and use a Content Block:
1. Insert the content block code into the layout or partial where you want to render content. For example, in the `<head>` of the layout:
```
// Layout: `application.html`
<head>
  <title>Airship CMS | {{#block 'page-title'}}Welcome!{{/block}}</title>
</head>

```
The name of this `block` is `page-title`. The text between the opening and closing `block` tags indicates the default markup to use if no unique markup is provided by the template.  

2. On the template, include a `content_for` to indicate what you want to render inside the `block`. `content_for` markup will not render on the page, so you can put it anywhere on a template. It is typical to insert it at the bottom of a template.
```
// Page Template: `about.html`

{{#content_for 'page-title'}}
  {{name}}
{{/content_for}}
```
```
// Page Template: `contact.html`

{{#content_for 'page-title'}}
  {{name}}
{{/content_for}}
```
HTML Output on About Page
```
<head>
  <title>Airship CMS | About</title>
</head>
```
HTML Output on Contact Page
```
<head>
  <title>Airship CMS | Contact</title>
</head>
```
HTML Output on Homepage
```
<head>
  <title>Airship CMS | Welcome!</title>
</head>
```
No `content_for` was included on the `_root.html` template, so the default text renders.

### Inserting Partials on Layouts with Content Blocks
@TO_DO: Add the TRACKING partial example

### Double versus triple brackets
If your `block` or `content_for` includes html, be sure to include it with triple curly brackets, so the html markup is included as markup, instead of literally rendered.

### Content Block Limitations
`block` can only access data from the current template being rendered. For example, if you are rendering the "About" page, a `block` cannot grab "Contact" page data and render it on the about page. For this type of functionality, you might want to add a related datafield to the page or use the Airship API to gain access to the related page's data.

See Airship API
See Relationships
