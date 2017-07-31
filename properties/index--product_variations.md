### `product_variations.id`
This is the ID of the variation given by Airship CMS.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>1954</p>
<p>1955</p>
```


### `product_variations.aerostat_id`
This is the ID of the variations root product given by Airship CMS.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{aerostat_id}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>3471</p>
<p>3471</p>
```


### `product_variations.product_variation_title`
This is the identifier or name of the product variation.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{product_variation_title}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Cat Food</p>
<p>Dog Food</p>
```


### `product_variations.product_variation_image`
Example Markup:
```
{{#each items}}{{#each product_variations}}
{{/each}}{{/each}}
```

Example Output:


### `product_variations.product_variation_description`
This is a short text description of the product variation.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{product_variation_description}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
<p>Lorem ad voluptatibus amet fugit excepturi facilis? Officiis repudiandae eius aspernatur ab reiciendis. Velit minima laudantium suscipit dolores soluta esse quo iste. Delectus culpa ad eveniet totam ratione! Maxime laboriosam.</p>
```


### `product_variations.price`
This is the regular price of the product.

The `{{format_currency}}` helper is useful for fields that contain currency values. For more information, see the [format_currency](Propeller-Helpers.md#format_currency) documentation.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>Price: {{format_currency price "usd"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Price: $5</p>
```


### `product_variations.sale_price`
This represents the products sale price if available.

The `{{format_currency}}` helper is useful for fields that contain currency values. For more information, see the [format_currency](Propeller-Helpers.md#format_currency) documentation.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>Sale Price: {{format_currency sale_price "usd" 2}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Sale Price: $3.00</p>
```


### `product_variations.weight`
This is the weight of the product in pounds and/or ounces.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{weight}}</p>
{{/each}}{{/each}}
```

Example Output:


### `product_variations.in_stock`
This shows whether or not the product variation is in stock.

Example Markup:
```
{{#each items}}{{#each product_variations}}
  {{#if in_stock}}
  <p>{{product_variation_title}}</p>
  {{else}}
  <p class="sold-out">{{product_variation_title}}</p>
  {{/if}}
{{/each}}{{/each}}
```

Example Output:
```
<p class="sold-out">Bird Toy</p>
<p>Hedgehog Toy</p>
```


### `product_variations.inventory`
This is the available amount of product.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{inventory}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>0</p>
<p>5</p>
```


### `product_variations.sorting_position`
This represents the sort order value of the variation.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{sorting_position}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>0</p>
<p>1</p>
```


### `product_variations.published_on`
This is the timestamp of when the variation was published.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{format_date published_on "D" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Wednesday, May 30, 2017</p>
<p>Wednesday, May 29, 2017</p>
```


### `product_variations.on_sale`
This shows whether or not the variation is currently on sale for a discounted price.

Example Markup:
```
{{#each items}}{{#each product_variations}}
  {{#if on_sale}}
  <p>{{product_variation_title}} for <span class="sale-price">{{format_currency this.sale_price "usd" 2}}</span></p>
  {{else}}
  <p>{{product_variation_title}} for {{format_currency this.price "usd" 2}}</p>
  {{/if}}
{{/each}}{{/each}}
```

Example Output:
```
<p>Bird Toy for <span class="sale-price">$8.00</span></p>
<p>Dog Food for $5.00</p>
```


### `product_variations.created_at`
This is the timestamp for when the variation was created.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{format_date created_at "D" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Wednesday, May 17, 2017</p>
<p>Wednesday, May 17, 2017</p>
```


### `product_variations.updated_at`
This is the timestamp for when the variation was updated.

Example Markup:
```
{{#each items}}{{#each product_variations}}
<p>{{format_date updated_at "D" "us"}}</p>
{{/each}}{{/each}}
```

Example Output:
```
<p>Thursday, June 01, 2017</p>
<p>Thursday, June 01, 2017</p>
```
