# Airmail Email Receipt Template
This template is used to customize receipt emails.

The following are examples of how to access available properties and fields:


## Property: `shipping_address`
Example Markup:
```
        <p style="border: 0; color: #32343C; font: inherit; font-family: 'Open Sans', 'Helvetica', sans-serif; font-size: 13px; line-height: 20px; margin: 0; padding: 0; vertical-align: baseline;">
          {{shipping_address.first_name}} {{shipping_address.last_name}}
          <br>
          {{shipping_address.address_1}}
          {{#if shipping_address.address_2}}
            <br>{{shipping_address.address_2}}
          {{/if}}
          <br>
          {{shipping_address.city}}, 
          {{#if shipping_address.other_location}}
            {{shipping_address.other_location_text}}, 
          {{else}}
            {{shipping_address.state}}, 
          {{/if}}
          {{shipping_address.country}}, {{shipping_address.zipcode}}
          {{#if shipping_address.phone_number}}
            <br>Phone: {{shipping_address.phone_number}}
          {{/if}}
        </p>
```


### Property `items`
Example Markup:
```
          {{#each items}}
            <tr style="border: 0; font: inherit; font-size: 100%; margin: 0; padding: 0; vertical-align: baseline;">
              <td style="border: 0; box-sizing: border-box; color: #676767; font: inherit; font-family: 'Open Sans', 'Helvetica', sans-serif; font-size: 13px; height: 30px; line-height: 20px; margin: 0; padding: 0; padding-right: 15px; vertical-align: middle;">
                {{#each product_variations}}
                  {{this.product_variation_title}}
                {{/each}}
              </td>
              <td style="border: 0; box-sizing: border-box; color: #676767; font: inherit; font-family: 'Open Sans', 'Helvetica', sans-serif; font-size: 13px; height: 30px; line-height: 20px; margin: 0; padding: 0; padding-right: 15px; vertical-align: middle;">{{this.quantity}}</td>
              <td style="border: 0; color: #676767; font: inherit; font-family: 'Open Sans', 'Helvetica', sans-serif; font-size: 13px; height: 30px; line-height: 20px; margin: 0; padding: 0; text-align: right; vertical-align: middle;">
                {{#each product_variations}}
                  {{format_currency this.price "usd" 2}}
                {{/each}}
              </td>
            </tr>
          {{/each}}
```
