1. Start a Project.
<p>If you don't have a free Airship account yet, <a href="/signup">sign up</a> for one to access the Skyport Developer Portal. Launch a new site, then follow the link in the confirmation email to the Airship CMS Admin panel. This is where you can manage your users (accounts for content creators or other developers), and set up the data structure for the site.</p>

2. Build your schema & relationships.
<p>Plan out the sitemap and sketch quick wireframes for each unique page or collection in your project. If you need to see some examples, we have some demo <a href="/use-cases">use cases</a> to share that are schemas from our own actual projects.</p>
<p>In Airship CMS, define the dynamic datafields needed for each Page and Collection. Remember that any datafield that you define directly maps to a piece of content or value that you would want your Content Creator to be able to update by themselves at any time.</p>
<p>If you aren't sure about the exact datafields you need, don't worry! Just start with the Landing Page and the example Collection that are defined for you. You can make changes and additions to the site at any time.</p>
<p>Once you are done setting up the site structure, add some demo content to each Page and add some placeholder items to each Collection. Be sure to do this step, so you will be able to see content on the scren when you are developing your project.</p>

3. Install Airship Launcher.
<p>Install the Airship Launcher so you have access to the command line tools necessary for serving site content when you are developing locally.</p>
<p><em>You can skip this step if you already have airship launcher installed. Not sure? Type this in your terminal. If you see a version number, you are already good to go!</em></p>
<pre>airship version</pre>
<p><b>Quick Install</b></p>
<pre>
/bin/sh -c "$(curl -fsS https://install.airshipcms.io)"
</pre>
<p><b>Slow Install</b>
For those of you that want to see exactly what tools are being installed on your machine, read and follow the instructions at <a href="https://install.airshipcms.io">install.airshipcms.io</a>.

4. <span class="code">airship login</span> to access your project content.
<p>Create a new empty directory for your project.</p>
<pre>
mkdir ~/MyFirstAirshipSite
cd ~/MyFirstAirshipSite
</pre>
<p>If you use an SCM like Git (you should be!), then you can initialize this directory as a versioned project.</p>
<p>Inside of the <span class="code">~/MyFirstAirshipSite directory</span>, run this command (replace "yourairshipsubdomain" with your actual subdomain:</p>
<pre>
airship login yourairshipsubdomain</span>
</pre>
<p>A browser window will pop up prompting you to login through Auth0 (our authentication provider). Once you log in successfully, you can close the browser window.</p>

5. <span class="code">airship land</span> to retrieve files.
<p>Once you are logged in, you need to sync your local project directory with the templates and files generated when you set up your site schema in Airship CMS. All airship commands should be done inside of your <span class="code">~/MyFirstAirshipSite</span> directory.</p>
<pre>airship land</pre>
<p>This command will generate a <span class="code">compartments</span> directory containing critical Airship files that are necessary for building out your project templates. Running <span class="code">airship land</span> will overwrite any files in the <span class="code">compartments</span> directory, so please be very aware of when you run this command, and back up local files often! You will typically only need to <span class="code">airship land</span> once per project during this setup phase. After your files are landed, you will be working locally on your project (and hopefully backing up code to an SCM), so you probably won't need to land the project again.</p>
<p>Now that you have synced all the files that were on the server, you can start developing!</p>

6. <span class="code">airship serve</span> for local development.
<p>You can start a local development server by using the Airship Launcher serve command.</p>
<pre>
airship serve
</pre>
<p>You must leave this terminal open during development in order to access the local server, so you probably want to have at least two terminals open.
</p>

7. Change files & link to content fields.
<p>While the server is running, you can test out your site locally by navigating to <span class="code">localhost:9001</span>.
<p>The local development site pulls live content from the Airship database, so internet access is required.</p>
<p>You can add and update layouts, templates, and media assets during development, refresh the local server, and see the local changes right away.</p>

8. <span class="code">airship launch</span> to publish your project.
<p>Once a version of your site is ready to launch to production, run this command to deploy your templates and assets:</p>
<pre>airship launch</pre>
<p>In your terminal, you will be presented with a preview of the actions that will occur when you run <span class="code">airship launch</span>. Review the actions carefully before confirming, then enter <span class="code">y</span> or <span class="code">yes</span>.
<p>Once you confirm and launch, then your site will be updated immediately!</p>

9. Back up files with your own source code management tool.
<p>Part of your regular development workflow probably involves using a Source Code Management tool like Git, where you can maintain your own versioning and backups. SCM tools work seamlessly with Airship projects. You can put any files you want in your main repository directory, as long as the <span class="code">compartments</span> directory maintains proper files and structure.</p>
<p>Another good practice during development, is to have a staging environment. This is relatively simple with Airship. Just create a new Airship site for each environment that you need for Quality Assurance, User Acceptance Testing, and Production. For sites that have a more complex eCommerce functionality that requires a lot of testing, we have a separate staging server that is set to the development mode of Stripe.</p>
