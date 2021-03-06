The `related_items` field is useful for creating relationships between pages and collections, or collections and collections.

When rendering `{{{help}}}`, related items appears in list of `related_items` instead of within `{{fields}}`. Related items can be rendered with the `{{#each}}` helper, since it is an array of items. When the `{{#each}}` propeller is used, the order that items are rendered is set by the sorting position of the items set in Airship CMS. If dot notation for rendering is preferred, the item's sorting position (array index) is required in the markup.

Example markup using related items with the variable name `similar_animals`:
```
<div class="similar-animals">
  {{#each related_items.similar_animals}}
  <h4><a href="{{slug}}">{{fields.name}}</a></h4>
  {{/each}}
</div>
```

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/hedgehog">Hedgehog</a></h4>
  <h4><a href="/mammals/view/bobcat">Bobcat</a></h4>
</div>
```

Alternatively the `{{#sort_list}}` propeller can be used to render items. The `{{#sort_list}}` propeller will take precedence over the order determined in Admin. Example markup rendering related aerostats using the {{#sort_list}} propeller:
```
<div class="similar-animals">
  {{#sort_list related_items.similar_animals sort="fields.name" order="asc"}}
  <h4><a href="{{slug}}">{{fields.name}}</a></h4>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/bobcat">Bobcat</a></h4>
  <h4><a href="/mammals/view/hedgehog">Hedgehog</a></h4>
</div>
```

Example markup using dot notation to render the second item in related aerostats with variable name `similar_animals`:
```
<div class="similar-animals">
  <h4><a href="{{related_items.similar_animals.1.slug}}">{{related_items.similar_animals.1.fields.name}}</a></h4>
</div>
```

You may also optionally wrap the item's index with brackets: `{{related_items.similar_animals.[1].fields.name}}`

Example Output:
```
<div class="similar-animals">
  <h4><a href="/mammals/view/bobcat">Bobcat</a></h4>
</div>
```

Limitations:
- `related_items` data attached to collection items will not render on a collection `index.html` template.
- `related_items` data attached to collection items will not render on a collection `category.html` template.
- `related_items` data attached to a page will not render on a page template.

Notes: 
- Fields such as `{{permalink}}` which contain content outside the `{{#each}}` can still be accessed by prepending `../` to the variable name, like this: `{{../permalink}}`
- On an `index.html` and `category.html` the list of `items` will hide `related_items` content.
