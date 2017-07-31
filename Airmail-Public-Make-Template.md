# Public Make Email Templates
 To use public make email templates, you must create a collection in Admin with public make enabled, and with fields that will hold each item of information you would like submitted.

Example Markup of a public make email template:
```
<h3>You have a new Contact Form Inquiry.</h3>
<p>Submitted: <strong>{{created_at}}</strong></p>
<hr /> 
<h3>Customer Details:</h3>
<p>Name: <strong>{{fields.name}}</strong>
<br>Email: <strong>{{fields.email}}</strong>
<br>Phone: <strong>{{fields.phone}}</strong>
<hr /> 
<h3>Message:</h3>
<p>{{fields.message}}</p>
<hr /> 
<p><em>Please do not reply to this automated email.</em></p>
```

## Airmail Public Make Properties:
The following properties can be rendered from an airmail public make template:

- id [single--id]
- published_on [single--published_on]
- created_at [single--created_at]
- updated_at [single--updated_at]


The following field types can be rendered on an airmail public make template:

- `text`
- `textarea`
- `richtext area`
- `image`
- `link`
- `number`
- `radio`
- `select`
- `multiselect`
- `checkbox`
- `list of images`
- `list of links`
- `date`
