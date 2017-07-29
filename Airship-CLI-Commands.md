# Airship Launcher CLI
Airship Launcher is the set of command line tools that allow developers to connect to the Airship CMS server while developing projects locally. Developers can login to their Airship account, serve content from the CMS, and deploy projects from the command line with the Airship Launcher toolkit.

Only users with superadmin access can use the CLI.

---

## `airship login subdomain`
Log in to your project. Use only the airship subdomain of your project or the full airship url of your project. You cannot login with CNAMEs that have been pointed to your site.
```
airship login subdomain
```
or
```
airship login subdomain.airshipcms.io
```
(_replace subdomain with your actual subdomain_). 

Example: If your airshipcms.io project subdomain is "marketing" and the site is "marketing.airshipcms.io", you would enter 
```
airship login marketing```
or
```
airship login marketing.airshipcms.io
```
This will connect you to the airship server for your project.

## `airship land`
This downloads all server templates and files and replaces your local copies.
```
airship land
```
Do this the first time you work on the project. This pulls down necessary Airship config files and initial project structure. After your initial land, you probably have all your files frequently backed up in Git, so you won't have to run `airship land` anymore, and you can simply create and launch new files.

If for some reason you need to re-sync files, you can run `airship land`. Be sure you have backed up your local files because airship land will overwrite them.

## `airship launch`
This uploads all local templates and files and replaces the server copies.
```
airship launch
```

When you are ready to launch your local changes to production, run `airship launch`. This will overwrite all files on the server to match your local project structure. If you have added files locally, they will be added to the server. If you have deleted files locally, they will be deleted from the server.

If for some reason you need to back up the state of production `compartments`, you can `airship land` files into a separate directory for storage.

### Not a Replacement for Git
`airship land` and `airship launch` are meant to be publishing and syncing tools only. They do not replace the purpose of a source code management tool. For a typical project, you only need to run airship land once. After that you will just be running airship launch to add changes to your live site.

### Debugging after `airship launch`
If you launched your project and you don't see your changes on the live site, try doing a hard-refresh on the browser for the live site. If that doesn't work, try clearing your browser cache. Your local cache may be very sticky. If that doesn't work either and it has been more than 5 minutes since you have launched your site, there might be some other issue.

## `airship serve`
This renders content from Airship CMS. Keep this running in a dedicated a terminal to keep an active connection to the server.
```
airship serve
```

## `airship logout`
This logs you out of the site you are connected to.
```
airship logout
```

## `airship upgrade`
This upgrades your CLI tools. Most updates are optional. If an update is required, you will be forced to upgrade before you can execute any CLI commands.
```
airship upgrade
```

## `airship`
This lists all airship cli commands.
```
airship
```
