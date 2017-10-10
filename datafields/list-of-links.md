The `list of links` field can be rendered using the `{{#each}}` helper, since it is an array of items. When the `{{#each}}` propeller is used, the order that items are rendered is controlled by the sorting position of the items set in Airship CMS. If dot notation for rendering is preferred, the item's sorting position (array index) is required in the markup.

Example markup using a `list of links` with the variable name `additional_links`:
```
<div class="additional-links">
  {{#each fields.additional_resource_links}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
    <p>{{../permalink}}</p>
  </div>
  {{/each}}
</div>
```

Example Output:
```
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io/">Resource: link</a>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio</p>
    <p>Dolor illo in iure volupta sed totam quod.</p>
    <p>additional-links</p>
  </div>
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: other link</a>
    <p>Lorem ipsum dolor rem nam sequi ea</p>
    <p>Lorem adipisci iusto quia quibusdam rem dicta voluptates, placeat similique quas minima!</p>
    <p>additional-links</p
  </div>
</div>
```

Alternatively the `{{#sort_list}}` propeller can be used to render items. The `{{#sort_list}}` propeller will take precedence over the order determined in Admin. Example markup rendering the list of links using the `{{#sort_list}}` propeller:
```
<div class="additional-links">
  {{#sort_list fields.additional_resource_links sort="title" order="desc"}}
  <div class="link">
    <a href="{{url}}">Resource: {{title}}</a>
    <p>{{subtitle}}</p>
    <p>{{caption}}</p>
    <p>{{../permalink}}</p>
  </div>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: other link</a>
    <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio</p>
    <p>Dolor illo in iure volupta sed totam quod.</p>
    <p>additional-links</p>
  </div>
  <div class="link">
    <a href="http://marketing.airshipcms.io/">Resource: link</a>
    <p>Lorem adipisci iusto quia quibusdam rem dicta voluptates, placeat similique quas minima!</p>
    <p>Lorem ipsum dolor rem nam sequi ea</p>
    <p>additional-links</p>
  </div>
</div>
```

Note: Fields such as `{{permalink}}` which contain content outside the `{{#each}}` can still be accessed by prepending `../` to the variable name, like this: `{{../permalink}}`

Example markup using dot notation to render the second item in a list of links with variable name `additional_links`:
```
<div class="additional-links">
  <div class="link">
    <a href="{{fields.additional_resource_links.1.url}}">Resource: {{fields.additional_resource_links.1.title}}</a>
    <p>{{fields.additional_resource_links.1.subtitle}}</p>
    <p>{{fields.additional_resource_links.1.caption}}</p>
  </div>
</div>
```

You may also optionally wrap the item's index with brackets: `{{fields.additional_resource_links.[1].title}}`

Example Output:
```
<div class="additional-links">
  <div class="link">
    <a href="http://marketing.airshipcms.io">Resource: other link</a>
    <p>Lorem ipsum dolor rem nam sequi ea</p>
    <p>Lorem adipisci iusto quia quibusdam rem dicta voluptates, placeat similique quas minima!</p>
  </div>
</div>
```
