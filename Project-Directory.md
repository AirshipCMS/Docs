# Project Directory
The following explains the local development structure of an Airship Project.

---

## Directory Structure
The directory structure of an Airship Project will look like this:
```
.
├── .airship
│  └── name
└── compartments
   ├── airmail
   ├── assets
   │   ├── media
   │   ├── scripts
   │   └── styles
   ├── layouts
   │   └── application.html
   ├── partials
   └── templates
       └── root.html
```
Any directories and files may be placed outside of `/compartments`. Files outside `/compartments` will be ignored when your project is published.

## .airship
The `.name`  directory contains a file called `name`. The `name` file identifies the subdomain of your project whenever you run `airship serve`, `airship launch`, or `airship land`.

## compartments
The `compartments` directory should only contain the following subdirectories:
- airmail
- assets
- layouts
- partials
- templates

### Do not add any other directories immediately inside `compartments`.
Do not add any other directories immediately inside `compartments`. If you do this, your site will behave normally when you are developing locally, however extraneous directories ( not sure: will be ignored? will not launch? will cause errors during launch? ).

## airmail
The `airmail` directory contains templates for emails. The `airmail` directory should contain only html files. It should not contain any other filetypes or subdirectories. Every template in the `airmail` has a specific filename and a specific function. See [Airmail Email Templates](/documentation/view/airmail-email-templates) for more information on email templating.

## assets
Any assets and subdirectories can be added to the `assets` directory. Standard directories typically in this directory are `media` (contains images and files), `scripts` (contains javascript files), and `styles`(contains css). However, you can set up any subdirectory structure within the `assets` directory.

To reference any files located within assets, referece them with an absolute path to the root:
- `/assets/scripts/app.js`
- `/assets/styles/styles.css`
- `/assets/media/logo.png`
- `/assets/team-images/2017/jon.png`

Anything stored in the `assets` directory uploads to the Airship CDN, hosted on [Cloudinary](http://cloudinary.com).

File Restrictions:
- Maximum Filesize: 10MB
- Most File Types are Allowed. Disallowed File Types: 'action', 'apk', 'app', 'bat', 'bin', 'cmd', 'com', 'command', 'cpl', 'csh', 'exe', 'gadget', 'inf1', 'ins', 'inx', 'ipa', 'isu', 'job', 'jse', 'ksh', 'lnk', 'msc', 'msi', 'msp', 'mst', 'osx', 'out', 'paf', 'pif', 'prg', 'ps1', 'reg', 'rgs', 'run', 'sct', 'shb', 'shs', 'u3p', 'vb', 'vbe', 'vbs', 'vbscript', 'workflow', 'ws', 'wsf'.

## layouts
only html. no directories. layouts should match those set in modify in admin panel (or they will simply be unused layouts. see template rendering `application.html` is the only layout you get when you generate an unmodified site.


## templates
only html files and directories here. see page templates and template directories. `root.html` is the only template you get when you generate an unmodified site.

---

## Other Files
you can add any custom files outside the compartments directory. etc. they won't be landed/launched with your project. (good idea to use scm)

see more at boilerplates & examples etc
