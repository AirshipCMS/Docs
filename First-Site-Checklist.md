# First Site Checklist
Complete this checklist after completing the Quickstart Guide. Each task is meant to encourage you to read relevant Documentation that will help you complete. Once all items are checked, you should be fairly comfortable with basic Airship templating, rendering, asset management, and deployment patterns.

---

- [ ] Move the embedded stylesheet located in the `application.html` into a `styles.css` external stylesheet located in the `/assets/` directory. Within the `application.html` layout, link to the external stylesheet. All files within the assets directory can be accessed with a link that starts with the relative reference `/assets/...`.

- [ ] In your local project directory, manually create a new **Layout** named `homepage.html` that is a copy of `application.html`, then in the Admin Portal, set it as the layout for the `root.html` page.

- [ ] Edit the new `homepage.html` layout, so that it has a `<nav>` list of links to all pages on the site. Good Practice: Page links should be relative to the subdomain, so instead of `<a href="https://mysite.airshipcms.io/about">About</a>`, set the link to be  `<a href="/about">About</a>`
