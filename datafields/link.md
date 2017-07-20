This field is useful for rendering a link, or a text of text information. Although an image is a single item, it shares the same propellers markup as a list of images. It must be rendered with an `{{#each}}` helper. 

The `link` field has inputs for `title`, `subtitle`, `url`, and `caption`. Example markup using a link field with the variable name `resource_link`:
```
<div class="link">
  {{#each fields.resource_link}}
  <a href="{{url}}">Resource: {{title}}</a>
  <p>{{subtitle}}</p>
  <p>{{caption}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshipcms.io/">Resource: Animal Info</a>
  <p>Dolor illo in iure voluptas sint?</p>
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```

Note: if you need to access top-level properties such as a page or item's `{{permalink}}`, within an `{{#each}}` you can do so with `../` markup prepending the property. Example:
```
<div class="link">
  {{#each fields.resource_link}}
  <a href="{{url}}">Resource: {{title}}</a>
  <p>{{subtitle}}</p>
  <p>{{caption}}</p>
  <p>{{../permalink}}</p>
  {{/each}}
</div>
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshipcms.io/">Resource: Animal Info</a>
  <p>Dolor illo in iure voluptas sint?</p>
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
  <p>animal-info</p>
</div>
```
