# Form Creation Guide
Download the repository files at [https://github.com/AirshipCMS/endtoend.airshipcms.io](https://github.com/AirshipCMS/endtoend.airshipcms.io). See an example of the live form at [https://endtoend.airshipcms.io/contact](https://endtoend.airshipcms.io/contact).

---

In Airship CMS, create a Collection that has fields that correlate to the data you want to save in your form. **It is easiest to save all data as Text**, though if you want to manipulate data after submission, you can also save data as radio, select, and checkbox field types.

## Collection Setup
Pay attention to the **Public Path**. This is important for creating the email template for this form.
![collection-setup](https://user-images.githubusercontent.com/1865400/29060441-806f6dd8-7bb5-11e7-99cf-f7ad80740e4d.png)

## Collection Rendering
Skip this. You don't need to set a layout or template directory.

## Collection Settings
![collection-settings](https://user-images.githubusercontent.com/1865400/29060440-8060e506-7bb5-11e7-906d-aa2abbcccf5d.png)

## Post Fields
![post-fields](https://user-images.githubusercontent.com/1865400/29060442-806f825a-7bb5-11e7-9397-a5d28f5cba0c.png)

## Primary Label
Leave it as Created At.
![primary-label](https://user-images.githubusercontent.com/1865400/29060439-805c424e-7bb5-11e7-94df-29c382b55dd1.png)

## Find the Collection ID.
Save the Collection. Then reopen the Modify View, and find the **Collection ID**.
![collection-id](https://user-images.githubusercontent.com/1865400/29060438-805c1918-7bb5-11e7-8030-0488b826b0ee.png)

---

### Untested Field Types
Field types that have not been tested with forms: Multiselect, Richtext Area, Image, Link, List of Images, List of Links, Related Aerostats, Date.




must add bcc public make email
or will submit without notifying
cannot email user for security

must launch templaees
