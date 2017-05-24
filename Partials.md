# Partials
A partial let you store a snippet of markup as a separate file, so you can reuse common code blocks in multiple layouts and templates. 

To create and use a partial:
1. Create a file in `/compartments/partials/`, such as `subnav.html`
1. Add markup to the partial. The partial has access to any data and properties _relative to the template or layout that it is inserted into_.*
1. Render a partial by adding the partial helper to the markup. Your partial name will match the partial filename. This example shows a reference to the partial called `subnav.html`.
```
// Partial: `subnav.html`

<ul class="subnav active-{{permalink}}">
  <li class="home"><a href="/">Home</a></li>
  <li class="about"><a href="/">About</a></li>
  <li class="contact"><a href="/">Contact</a></li>
</ul>
```
```
// Located on a Page Template
{{> subnav }}
```

### Partial Blocks
If you want to change some of the markup in the partial based on the template rendered, you can do so with a `partial-block`.

For example, you may want to use a partial for a subnav component where the heading changes depending on the page being rendered. A `partial-block` will not render on the page, so you can put it anywhere on a template. It is typical to insert it at the bottom of a template.
```
// Partial: `subnav.html`

<h3>{{@partial-block}}</h3>
<ul class="subnav active-{{permalink}}">
  <li class="home"><a href="/">Home</a></li>
  <li class="about"><a href="/">About</a></li>
  <li class="contact"><a href="/">Contact</a></li>
</ul>

```
```
// Page Template: `about.html`

{{#> subnav}}
  More About This Site
{{/subnav}}

```
```
// Page Template: `contact.html`

{{#> subnav}}
  Other Ways to Contact Us
{{/subnav}}

```
HTML Output on About Page
```
<h3>More About This Site</h3>
<ul class="subnav active-about">
  <li class="home"><a href="/">Home</a></li>
  <li class="about"><a href="/">About</a></li>
  <li class="contact"><a href="/">Contact</a></li>
</ul>
```
HTML Output on Contact Page
```
<h3>Other Ways to Contact Us</h3>
<ul class="subnav active-contact">
  <li class="home"><a href="/">Home</a></li>
  <li class="about"><a href="/">About</a></li>
  <li class="contact"><a href="/">Contact</a></li>
</ul>
```

### Inserting Partials on Templates
A partial has access to any properties relative to the template or layout that it is added to. If you add the partial to a template, you will have access to all template properties. 

In the above examples, the markup inserted in place of `partial-block` contains only static text. In the case where you are inserting a partial onto a template, you may want to include dynamic data from the template into the partial. There are a few ways to use dynamic data:

#### Method 1: Add propellers directly to the partial, instead of inside the `partial-block`  
Add propellers directly to partial, instead of in the `partial-block`. This is shown in the previous example, where the active class is applied to the `ul` element.
```
// Partial: `subnav.html`
<ul class="subnav active-{{permalink}}">
  <li class="home"><a href="/">Home</a></li>
  <li class="about"><a href="/">About</a></li>
  <li class="contact"><a href="/">Contact</a></li>
</ul>
```
This works if the partial is only used on page templates. It won't work for the `index.html`, `categories.html`, and `category.html` templates for a collection.

#### Method 2: Prepend `../` to template properties referenced within a `partial-block`.  
This is necessary because the scope of the `partial-block` is limited to the context of the `partial`. The `../` tells the `partial-block` to look in the `partial`'s parent scope (the template) to access the property.
```
// Partial: `short-title.html`
<h3>{{@partial-block}}</h3>
```
```
// Page Template: `about.html`
{{#> short-title}}
  {{../fields.page-header}}
{{/short-title}}
```
```
// Page Template: `contact.html`
{{#> short-title}}
  {{../fields.page-header}}
{{/short-title}}
```

#### Method 3: Use Params to set variables that can be inserted into the partial.
```
// Partial: `interesting-things.html`
<p class="favorite-page">
  {{ myParam1 }} | {{ myParam2 }}
</p>
```
```
// Page Template: `about.html`
{{> interesting-things myParam1=fields.title myParam2=permalink}}  
```
```
// Page Template: `contact.html`
{{> interesting-things myParam1="Hello this is Awesome!" myParam2=permalink}}

```
HTML Output on About Page
```
<p class="favorite-website">About | about</p>
```
HTML Output on Contact Page
```
<p class="favorite-website">Hello this is Awesome! | contact</p>
```

// Do Params only work for string types of data?

### Inserting Partials on Layouts
If you add a partial to a layout, you can easily create partials with static text. However, you won't have the right scope to access template properties. You can however, extend the functionality of a partial by using a content block inside a partial to access template properties.

See Content Blocks

### Double versus triple brackets
If your partial or `partial-block` includes html, be sure to include it with triple curly brackets so the html markup is included as markup, instead of rendered as text.

See Content Blocks

#### Partial Limitations
You can insert a partial into a template, layout, another partial, or even a Content Block. Do not recursively insert a partial into the same partial (your layout will break).
