# Project Directory
intro

---

## Directory Structure
```
diagram here
```

## .airship
contains .name  which identifies your project, the next time you login/serve/launch. if you change this, you will be unsyncing to your airship project.

## compartments
do not add any other files or directories at the first level of compartments.

## airmail
contains templates for emails. html files only. should not contain any other filetypes or directories.
templates in here have specific names and functions.
see rendering/templating for specific airmail templates as well as how to call/reference data within a template.

## assets
add any directories in here. standard directories are `media`, `scripts`, and `styles`, though you can put whatever you want.
max file size cloudinary.
banned file types cloudinary

## layouts
only html. no directories. layouts should match those set in modify in admin panel (or they will simply be unused layouts. see template rendering `application.html` is the only layout you get when you generate an unmodified site.


## templates
only html files and directories here. see page templates and template directories. `root.html` is the only template you get when you generate an unmodified site.

---

## Other Files
you can add any custom files outside the compartments directory. etc. they won't be landed/launched with your project. (good idea to use scm)
