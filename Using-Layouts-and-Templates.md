# Layouts & Templates
Layouts and templates are used for creating classically rendered websites.

---

## Layouts
[Layouts](/documentation/view/layouts) contain general markup that is shared across the pages and collections where the layout is set.

## Templates
Templates contain markup specific to a page or collection.

### Page Templates
[Page Templates](/documentation/view/page-templates) contain html and Page Propellers code that renders page content. 

### Collection Template Directories
[Collection Templates](/documentation/view/collection-templates) contain html and collection propellers code that renders collection items content. 

### Airmail Templates
An email is sent to the Admin Email(s) specified in Airship CMS whenever a public post is created for a collection with "public make" enabled. Emails are also sent when eCommerce transactions occur (creating Orders, Invoices, Subscriptions, and Shipments). See [Airmail Email Templates](/documentation/view/airmail-email-templates) for more information.

---

## Client-Side Rendering for SPAs
if you are building a single page application, you probably only need a template that loads on the root url for the spa. in airship, you can set which pages should behave like a spa.
