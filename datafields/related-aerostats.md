When rendering `{{{help}}}`, related items appears in a list of `related_items` instead of in `{{fields}}`. The `related aerostats` field requires the `{{#each}}` helper, since it is an array of items. When the `{{#each}}` propeller is used, the order that items are rendered is controlled by the order of items set in Airship CMS.

Example markup using related aerostats with the variable name `similar_animals`:
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

_Note how the outer fields can still be accessed using the `{{../variable_name}}` syntax._