The `link` field is useful for rendering a link, or bunch of text information. Although a link is a single item, it shares the same propellers markup as a list of links. It must be rendered with an `{{#each}}` helper. 

The `link` field has inputs for `title`, `subtitle`, `url`, and `caption`. Example markup using a link field with the variable name `resource_link`:
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
