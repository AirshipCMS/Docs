The `link` field is useful for rendering a link, or a bunch of text information. Although a link is a single item, it shares the same propellers markup as a list of links. It can be rendered using the `{{#each}}` helper, or using dot notation with the item's array index.

The `link` field has inputs for `title`, `subtitle`, `url`, and `caption`.

The following markup examples use a link field with the variable name `resource_link`:

Example markup using the `{{#each}}` helper:
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
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque.</p>
  <p>animal-info</p>
</div>
```

Note: Fields such as `{{permalink}}` which contain content outside the `{{#each}}` can still be accessed by prepending `../` to the variable name, like this: `{{../permalink}}`

Example markup using dot notation and the item's index in the array:
```
<div class="link">
  <a href="{{fields.resource_link.0.url}}">Resource: {{fields.resource_link.0.title}}</a>
  <p>{{fields.resource_link.0.subtitle}}</p>
  <p>{{fields.resource_link.0.caption}}</p>
</div>
```

Example Output:
```
<div class="link">
  <a href="http://marketing.airshipcms.io/">Resource: Animal Info</a>
  <p>Dolor illo in iure voluptas sint?</p>
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque.</p>
</div>
```
