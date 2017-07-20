An `image` field is useful for rendering an image or including a link to a file. Although an `image` is a single item, it shares the same propellers markup as a `list of images`. It must be rendered with an `{{#each}}` helper.

Example markup using an `image` field the variable name `animal_iamge`:
```
{{#each fields.animal_image}}
<div class="animal-image">
  <h1>{{../permalink}}</h1>
  <h6>{{title}}</h6>
  <p>{{subtitle}}</p>
  <img src="{{url}}" alt="">
  <p>{{caption}}</p>
</div>
{{/each}}
```

Example Output:
```
<div class="animal-image">
  <h1>hedgehog</h1>
  <h6>Grumpy Hedgie</h6>
  <p>Lorem ipsum dolor</p>
  <img src="http://res.cloudinary.com/airship/image/upload/v1494989137/media/hedgietest_rpaxih.jpg" alt="">
  <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
</div>
```

Note: Fields such as `{{permalink}}` which contain content outside the `{{#each}}` can still be accessed by prepending `../` to the variable name, like this: `{{../permalink}}`
