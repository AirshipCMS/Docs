# Related Items
Related items are the items selected in [related aerostat](/documentation/view/datafields#user-content-related-items) fields.

Each item is an item within a collection. Items must be published in order to be available for rendering. The content entered in Admin for each item is accessible through the `related_items.related_aerostats_variable_name` field. The order of which the items are rendered can be controlled by either dragging each item into the proper order while editing the page, or by using the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller.


## Using `{{#each}}` to render
See the [#each](/documentation/view/related-items#user-content-each) propeller documentation for more information.

Example markup rendering related aerostats with the variable name `similar_animals`:
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

## Using `{{#sort_list}}` to render
See the [#sort_list](/documentation/view/related-items#user-content-sort_list) propeller documentation for more information.

Example Markup:
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
