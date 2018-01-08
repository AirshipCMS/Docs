# 4. Edit Content in Airship CMS

Content that is changed in the Airship CMS Admin portal will update in both your live site and local development environment. To edit the demo content in the example starter Homepage, follow these steps:

---

## Edit the Homepage content. See it update locally & live.
Go to the Airship CMS admin panel for your site, and click on "Pages" in the sidebar.

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-pages.jpg">

Click the pencil icon <img width="27" alt="pencil" src="https://airshipcms.io/assets/media/quickstart-guide/icon-pencil.png"> for the "Homepage" of your site. It should look like this:  

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-initial.jpg">

Edit content. 

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-edit.jpg">

Save the page. Wait a few seconds, then refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)`. You will see the content update in both instances of the site. Sometimes it takes a few refreshes or a hard refresh to show content changes.

Local Site: 

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-edit-content.jpg">

Live Site:

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-live-edit-content.jpg">

## Edit the Homepage template. See it update locally (and _not_ update live).
Back in your text editor, open the `root.html` template located in `/compartments/templates`. Edit the button text. Save the file.

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-edit-template.jpg">

Refresh both your live site url in one tab `(https://mysite.airshipcms.io)` and your local site url in another tab `(http://localhost:9001)`. 

Local Site:

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-edit-template.jpg">

Live Site (same as before):

<img width="500" alt="CMS Homepage Initial" src="https://airshipcms.io/assets/media/quickstart-guide/browser-live-edit-content.jpg">

You will see that the markup has changed only in the _local instance of your site_. This is because in your local site, the page is rendered based on **local files** & **published content**, whereas the published site renders **published files** & **published content**. 

## See available properties and fields for a page with `{{{help}}}`.
On the `root.html` template add following markup at the very top of your page. Save the file.
```
{{{help}}}
```
In SublimeText 3, it will look like this:

<img width="500" alt="Text Editor Help" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-help.jpg">

In your browser, refresh your local site url `(http://localhost:9001)` and you will see a list of properties:  

<img width="500" alt="Browser Help" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-help.jpg">

Items in this list are the variable names for data that can be rendered on the _root_ page. The items listed inside the `fields` property correspond to fields that are set for the _root_ page in the <img width="26" alt="wrench" src="https://airshipcms.io/assets/media/quickstart-guide/icon-wrench.png"> Page Modify section in Airship CMS admin:  

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modify.jpg">

Content from Airship CMS is rendered by adding markup with the exact variable name listed in the `{{{help}}}` list, contained by double curly braces.

## Add a new field to the page.

### Add a New Field
On the Page Modify view in Airship CMS admin, add a new field to the page. This example adds the field `New Box`, type `text`.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modify-add-field.jpg">

Once the field is added to the list of fields, it will look like this:

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-modified.jpg">

Save the Modify view. If you refresh any browsers (locally or live), the new field _will not show_ because it has no value set, and it has not been added to the page markup.

### Add a Value for the New Field
Click the pencil icon <img width="27" alt="pencil" src="https://airshipcms.io/assets/media/quickstart-guide/icon-pencil.png"> for the "Homepage". Add some text for the new field "New Box":

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/cms-homepage-new-box.jpg">

### Refresh the browser for your local site
Refresh the browser for the local site. You will see the new field "new_box" added to the list of available page properties.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-help-new-box.jpg">

### Add markup for the new field
In your text editor, add markup to render the new field content:
```
{{fields.new_box}}
```

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-help-new-box.jpg">

You can comment out or delete the help markup if you don't need it anymore. The help list is meant to be a useful reference to help you while you are developing locally. `{{{help}}}` will not render anything on published sites.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/sublime-new-box.jpg">

### Refresh the browser for your local site
Refresh the browser for the local site. You will now see the content rendered for the new field.

<img width="500" alt="CMS Modify" src="https://airshipcms.io/assets/media/quickstart-guide/browser-local-new-box.jpg">

If you refresh the browser for the live site, you won't see the new field. You will need to run `airship launch` to make your changes live.

---

Next: Deployment

---

#### Skip to
Developer Login  
Deploymnet

#### Airship CMS features
Create Fields  
Create Pages  
Create Collections  





