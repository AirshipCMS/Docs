# Airmail Email Templates
An email is sent to the Admin Email(s) specified in Airship CMS whenever a public post is created for a collection with "public make" enabled.

Emails are also sent when eCommerce transactions occur (creating Orders, Invoices, Subscriptions, and Shipments).

---

## Requirements for Using Airmail Email Templates
- Be sure to turn on the "Public Make" Setting for the collection designated for form submissions.
- Be sure to have an `airmail.html` layout in your layout directory. This layout does not require any special content in the header, though it is required in order for airmail templates to work.
- Be sure to `airship launch` all airmail email templates. Airship will only use launched versions of your email templates.
- Be sure that there is at lease one email set in the BCC Emails list in Airship Admin.
- Be sure that email propellers syntax is correct. Any errors will cause the email to fail (and you will not receive any notifications).

## *_email.html
See the [Airmail Public Make Template](/documentation/view/airmail-public-make-template) for more information on emails for form submissions.

## Additional Templates
More information coming soon:
- receipt.html
- invoice.html
- shipment.html
- sub_receipt.html
- sub_active.html	
- sub_paid.html
- sub_failed.html
- sub_cancel.html
- sub_changed.html
- refund.html
