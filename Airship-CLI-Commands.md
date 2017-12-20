# Airship Launcher CLI
Airship Launcher is the set of command line tools that allow developers to connect to the Airship CMS server while developing projects locally. Developers can login to their Airship account, serve content from the CMS, and deploy projects from the command line with the Airship Launcher toolkit.

**Only users with superadmin access can use the CLI to run projects and develop locally.**

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

This will connect you to the airship server for your project.

## `airship land`
This downloads all server templates and files and **completely overwrites** your local copies.
```
airship land
```
`airship land` the first time you set up your local development workflow. `airship land` pulls down necessary Airship config files and your initial project structure. After you initially run `airship land`, you probably don't need to run `airship land` to retrieve files from the server, since you are probably using your own source code management system (like Git) to create backup copies of your code.

If for some reason you need to re-sync files, you can run `airship land`. Be sure to always back up up your local files! Running `airship land` will always overwrite your local files.

## `airship launch`
This uploads all local templates and files and replaces the server copies.
```
airship launch
```

When you are ready to launch your local changes to production, run `airship launch`. This will overwrite all files on the server to match your local project structure. If you have added files locally, they will be added to the server. If you have deleted files locally, they will be deleted from the server.

**Tip!** If for some reason you need to back up the current state of production `compartments`, you can `airship land` all production files into a separate directory for storage before launching your new set of files. Alternatively, if you are using a source code management system, you probably have a "production" branch and a "development" branch to organize live versus development files.

### Airship Commands are not replacements for Git Commands
`airship land` and `airship launch` are meant to be publishing tools only. They do not replace the purpose of a source code management tool.

## `airship serve`
This renders content from Airship CMS. Keep this running in a dedicated a terminal to keep an active connection to the server.
```
airship serve
```

You can keep an open connection to the airship server with `airship serve` for 24 hours. After 24 hours, you will be automatically disconnected, and you will need to `airship login` and `airship serve` to re-establish your connection to CMS data.

You can only `airship serve` a single Airship site at a time. If you run `airship serve` while another site is being served, the second serve command will have no effect.

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

### Debugging
If you launched your project and you don't see your changes on the live site, do a hard-refresh on the browser for the live site. If that doesn't work, clear your browser cache. Your local cache may be very sticky. If that doesn't work, and it has been more than 5 minutes since you have launched your site, there may be some other issue. See the [Airship CLI Troubleshooting](https://airshipcms.io/documentation/view/airship-cli-troubleshooting) page for development tips and assistance.
