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
The `.airship`  directory contains a file called `name`. The `name` file identifies the subdomain of your project whenever you run `airship serve`, `airship launch`, or `airship land`.

## compartments
The `compartments` directory should only contain the following subdirectories:
- airmail
- assets
- layouts
- partials
- templates

### Do not add any other directories immediately inside `compartments`.
Do not add any other directories immediately inside `compartments`. If you do, your site will behave normally when you are developing locally, however extraneous directories ( not sure: will be ignored? will not launch? will cause errors during launch? ).

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

### File Restrictions:
- Maximum Filesize: 10MB
- Most File Types are Allowed. Disallowed File Types: 'action', 'apk', 'app', 'bat', 'bin', 'cmd', 'com', 'command', 'cpl', 'csh', 'exe', 'gadget', 'inf1', 'ins', 'inx', 'ipa', 'isu', 'job', 'jse', 'ksh', 'lnk', 'msc', 'msi', 'msp', 'mst', 'osx', 'out', 'paf', 'pif', 'prg', 'ps1', 'reg', 'rgs', 'run', 'sct', 'shb', 'shs', 'u3p', 'vb', 'vbe', 'vbs', 'vbscript', 'workflow', 'ws', 'wsf'.

## layouts
The `layouts` directory should contain only html templates. It should not contain any subdirectories. Layout filenames should match those set in Modify section for a Page or Collection. Any extraneous layouts in the `layouts` directory will simply be unused layouts. By default, `application.html` is the only layout that is generated with a new site. See the Docs for more information on [Layouts](/documentation/view/layouts).

## templates
The `templates` directory should contain only html templates and subdirectories containing html temoplates. Template filenames and Template Directory names should match those set in Modify section for a Page or Collection. Any extraneous templates in the `templates` directory will simply be unused templates. By default, `root.html` is the only template that is generated with a new site. See the Docs for more information on [Page Templates](/documentation/view/page-templates) and [Collection Templates](/documentation/view/collection-templates).

---

## Other Files
Any directories and files may be placed outside of `/compartments`. Files outside `/compartments` will be ignored when your project is published.

If you are using a source code management tool like [Git](https://github.com), include all the contents of the `compartments` directory and `.airship` directory.

---

See some [Boilerplates and Examples](/documentation/view/boilerplates-and-examples) of Airship Projects
