# Form Creation Guide
Download the repository files at [https://github.com/AirshipCMS/endtoend.airshipcms.io](https://github.com/AirshipCMS/endtoend.airshipcms.io). See an example of the live form at [https://endtoend.airshipcms.io/contact](https://endtoend.airshipcms.io/contact).

---

## Step 1. Set up the Collection

### Collection Setup
Pay attention to the **Public Path**. This is important for creating the email template for this form.

![collection-setup](https://user-images.githubusercontent.com/1865400/29060441-806f6dd8-7bb5-11e7-99cf-f7ad80740e4d.png)

### Collection Rendering
Skip this. You don't need to set a layout or template directory.

### Collection Settings
![collection-settings](https://user-images.githubusercontent.com/1865400/29060440-8060e506-7bb5-11e7-906d-aa2abbcccf5d.png)

### Post Fields
Create fields that correlate to the data you want to save in your form. **It is easiest to save all data as Text**, though if you want to manipulate data after submission, you can also save data as radio, select, and checkbox field types. This example collection shows many different field types, though if you are making a simple contact form, you only need to set the field types you need:

![post-fields](https://user-images.githubusercontent.com/1865400/29060442-806f825a-7bb5-11e7-9397-a5d28f5cba0c.png)

### Primary Label
Leave it as Created At.

![primary-label](https://user-images.githubusercontent.com/1865400/29060439-805c424e-7bb5-11e7-94df-29c382b55dd1.png)

### Find the Collection ID.
Save the Collection. Then reopen the Modify View, and find the **Collection ID**.

![collection-id](https://user-images.githubusercontent.com/1865400/29060438-805c1918-7bb5-11e7-8030-0488b826b0ee.png)

---

## Step 2. Set a BCC Public Make Email
Go to **Settings** and add an email to BCC Public Make in order to receive emails when someone enters a form submission.

![bcc-publicmakesetting](https://user-images.githubusercontent.com/1865400/29060444-8078786a-7bb5-11e7-86ce-3d953ef88e52.png)

### Untested Field Types
Field types that have not been tested with forms: Multiselect, Richtext Area, Image, Link, List of Images, List of Links, Related Aerostats, Date.

---

## Step 3. Set up the Page for the form to render on.
For this example, a Page called "Contact" with permalink "/contact" and template "contact.html" was created.

![contact-page](https://user-images.githubusercontent.com/1865400/29060965-a47f227a-7bb7-11e7-88dc-10880e1ebf92.png)

---

## Step 4: Set up Page Template & Javascript to render & submit the form.
The javascript in `/assets/scripts/contact.js` is necessary for the form submission.
The above script file, and the referenced `jQuery` file are referenced at the bottom of the markup on the `contact.html` template.

With this markup & script, you can test that the form creates a post in the Contact Form Example collection.

An example post in the collection will look like this:

![submission-example](https://user-images.githubusercontent.com/1865400/29060885-5a3a62d8-7bb7-11e7-92cf-ef0b37837be7.png)

When you view the post fields, it will look something like this:

![post-fields](https://user-images.githubusercontent.com/1865400/29060442-806f825a-7bb5-11e7-9397-a5d28f5cba0c.png)

You will notice that even though the post has been created, you haven't received any email notifications.

---

## Step 5: Create Email Templates
must add bcc public make email
or will submit without notifying
cannot email user for security
must launch templaees
