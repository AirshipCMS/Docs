# Airship API
Airship API allows developers to extend the functionality of websites and web applications futher by allowing developers to create their own custom frontend solutions and connect to the Airship database. Airship API allows developers to combine classically rendered content with client-side rendered components to create fast-loading and robust user experiences.

---

## Airship Public API
Airship has a public API which is easy to use because any public resource can be accessed as json. (more information tba)

## Airship Private API
There is also a private API that you need to be logged into, and allows a way to create, update, and delete resources. You can create a custom single-page application that uses Auth0 Authentication if you need to create, update, or delete resoures in a way that is not standard within the Airship CMS backend.

When an Admin creates, updates, or deletes a resource, a webhook can be triggered on a separate server to request a custom payload from the resource. For example, if someone creates a "comment" on the site, it could trigger a webhook to notify another backend about the comment.

## Using Other APIs on Airship
Airship can serve up single-page applications, javascript, or jquery which create XHR requests to your API. You can pull any data that you want from your API and display the data on an Airship site. We have several clients doing this now.
