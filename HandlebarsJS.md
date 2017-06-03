# HandlebarsJS
See the [HandlebarsJS documentation](http://handlebarsjs.com/builtin_helpers.html) for their available built in helpers.

Be sure to check out the [Propeller Helpers documentation](Propeller-Helpers.md) for custom Airship CMS helpers such as [#sort_list](Propeller-Helpers.md#sort_list).

The following are some examples of using built in HandlebarsJS helpers to render Airship CMS content:


## {{#each}}
This is used to iterate over lists of items, which are notated with `[list]` when rendering `{{{help}}}` on any template page.

Example Markup:
```
{{#each items}}
<a href="{{slug}}"><h1>{{fields.name}}</h1></a>
{{/each}}
```

Example Output:
```
<a href="/mammals/view/anteater"><h1>Anteater</h1></a>
<a href="/mammals/view/anteater"><h1>Bobcat</h1></a>
<a href="/mammals/view/anteater"><h1>Camel</h1></a>
```

See the [HandlebarsJS #each documentation](http://handlebarsjs.com/builtin_helpers.html#iteration) for more information.


## {{#if}}
This is used to conditionally render elements if the given value is truthy. It can also be used in combination with `{{else}}` to render elements when the value is falsey.

Example Markup:
```
<div>
  {{#if fields.show_image}}
    <h3>Hedgehog</h3>
    {{#each fields.animal_image}}
      <img src="{{url}}" alt="">
    {{/each}}
  {{else}}
    <h3>Sorry! No image for this animal.</h3>
  {{/if}}
</div>
```

Example Output if `show_image` was checked:
```
<div>
    <h3>Hedgehog</h3>
    <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/hedgietest_rpaxih.jpg" alt="">
</div>
```

Example Output if `show_image` was not checked:
```
<div>
    <h3>Sorry! No image for this animal.</h3>
</div>
```

See the [HandlebarsJS #if documentation](http://handlebarsjs.com/builtin_helpers.html#conditionals) for more information.


## {{#unless}}
This is used to conditionally render elements if the given value is falsey. 

Example Markup:
```
{{#each items}}{{#unless fields.show_image}}
<p>Sorry! No image for this animal.</p>
{{/unless}}{{/each}}
```

Example Output _only_ if `show_image` was not checked:
```
<p>Sorry! No image for this animal.</p>
```

See the [HandlebarsJS #if documentation](http://handlebarsjs.com/builtin_helpers.html#unless) for more information.
