## 1. Start a Project.
Sign up for a free Airship account to access the **Airship Developer Portal**, then create your first project. In a few minutes, your site subdomain will be generated, and you can start development.

## 2. Get Familiar with the Airship CMS Admin Portal.
(Something)

## 3. Install Airship Launcher.
Install the Airship Launcher so you have access to the command line tools necessary for serving site content when you are developing locally.
<pre>
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
</pre>

## 4. <span class="code">airship login</span>
Create a new empty directory for your project, then login to your site:</p>
<pre>
airship login yoursubdomain</span>
</pre>
(_Replace "yoursubdomain" with your actual Airship subdomain._)
A browser window will pop up prompting you to login through Auth0 (our authentication provider). Once you log in successfully, you can close the browser window.

## 5. <span class="code">airship land</span>
Sync your local project directory with the templates and files used for the live site.</p>
<pre>airship land</pre>
This command will generate a <span class="code">compartments</span> directory containing critical Airship files that are necessary for building out your project templates. Running <span class="code">airship land</span> will overwrite any files in the <span class="code">compartments</span> directory, so please be very aware of when you run this command, and back up local files often!

## 6. <span class="code">airship serve</span>
You can start a local development server by using the Airship Launcher serve command:
<pre>
airship serve
</pre>

## 7. Change template markup
While the server is running, you can test out your site locally by navigating to <span class="code">localhost:9001</span>. The local development site pulls live content from the Airship database, so internet access is required. You can add and update layouts, templates, and media assets during development, refresh the local server, and see the local changes right away.

## 7. Change content
(content editing)

## 8. <span class="code">airship launch</span>
Run this command to deploy your templates and assets:
<pre>airship launch</pre>
In your terminal, you will be presented with a preview of the actions that will occur when you run <span class="code">airship launch</span>. Review the actions carefully before confirming, then enter <span class="code">y</span> or <span class="code">yes</span>.
Once you confirm and launch, then your site will be updated immediately!

---

## Ready for more?
See the entire Quickstart Guide.
Read the Docs.
