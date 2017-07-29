# Airmail Email Templates
An email is sent to the Admin Email(s) specified in Airship CMS whenever a public post is created for a collection with "public make" enabled.

Emails are also sent when eCommerce transactions occur (creating Orders, Invoices, Subscriptions, and Shipments).

---

## Requirements for Using Airmail Email Templates
Public Make turned on.

When using Airmail Email Templates, you need to `airship launch` templates in order for them to work. Airship will only use launched versions of your email templates.

You need to have BCC Emails Set in Airship Admin.

Syntax must be correct. Or it will break and you won't know it.

## receipt.html
See the [Receipt Email Template documentation](Airmail-Receipt-Template.md) for more information.

## invoice.html
See the [Invoice Email Template documentation](Airmail-Invoice-Template.md) for more information.

## *_email.html
See the [Public Make Template documentation](Airmail-Public-Make-Template.md) for more information.

## Additional Templates
More information coming soon:
- shipment.html
- sub_receipt.html
- sub_active.html	
- sub_paid.html
- sub_failed.html
- sub_cancel.html
- sub_changed.html
- refund.html
