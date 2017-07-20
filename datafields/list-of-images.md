The `list of images` field requires the `{{#each}}` helper, since it is an array of items. When the `{{#each}}` propeller is used, the order that items are rendered is controlled by the order of items set in Airship CMS.

Example markup using a list of images with the variable name `additional_animal_images`:
```
<div class="image-container">
  {{#each fields.additional_animal_images}}
  {{../fields.header}}
    <div class="image">
      <h6>{{title}}</h6>
      <img src="{{url}}" alt="">
      <p>{{subtitle}}</p>
      <p>{{caption}}</p>
    </div>
  {{/each}}
</div>
```

Example Output:
```
<div class="image-container">
  Cute Animals &amp; Products
    <div class="image">
      <h6>Sleepy Hedgie</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/cute-hedgehogs-311__700_reizde.jpg" alt="">
      <p>img from url</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
  Cute Animals &amp; Products
    <div class="image">
      <h6>Hedgie Dino</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/hedgietest2_a03l7y.jpg" alt="">
      <p>img from file</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
```

Alternatively the `{{#sort_list}}` propeller can be used to render items. The `{{#sort_list}}` propeller will take precedence over the order determined in Admin. Example markup rendering the list of images using the `{{#sort_list}}` propeller:
```
<div class="sorted-images">
  {{#sort_list fields.additional_animal_images sort="title" order="asc"}}
    <div class="image">
      <h6>{{title}}</h6>
      <img src="{{url}}" alt="">
      <p>{{subtitle}}</p>
      <p>{{caption}}</p>
    </div>
  {{/sort_list}}
</div>
```

Example Output:
```
<div class="sorted-images">
    <div class="image">
      <h6>Hedgie Dino</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989296/media/hedgietest2_a03l7y.jpg" alt="">
      <p>img from file</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
    <div class="image">
      <h6>Sleepy Hedgie</h6>
      <img src="http://res.cloudinary.com/airship/image/upload/v1494989229/media/cute-hedgehogs-311__700_reizde.jpg" alt="">
      <p>img from url</p>
      <p>Dolor illo in iure voluptas sint? Doloribus quae quos doloremque quae odio sequi facere animi at? Velit odit delectus optio dignissimos animi. Id iusto enim repellat veniam sed totam quod.</p>
    </div>
</div>
``` 

Note: Fields such as `{{permalink}}` which contain content outside the `{{#each}}` can still be accessed by prepending `../` to the variable name, like this: `{{../permalink}}`
