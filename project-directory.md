# project-directory

## .airship
contains .name  which identifies your project, the next time you login/serve/launch. if you change this, you will be unsyncing to your airship project.

## compartments
do not add any other files or directories at the first level of compartments.

### airmail
contains templates for emails. html files only. should not contain any other filetypes or directories.
templates in here have specific names and functions.
see rendering/templating for specific airmail templates as well as how to call/reference data within a template.

### assets
do not add any other files or directories at the first level of compartments.

#### media
can add any file type except ZYX. can add directories. cannot exceed X size.

#### scripts
can scripts such as XYZ. can add directories. cannot exceed X size. no server-side scripts. they will be ignored.

#### styles
styles ok. (is that only css??) can add directories. 

### layouts
only html. no directories. layouts should match those set in modify in admin panel (or they will simply be unused layouts. see template rendering

#### airmail.html
special layout for rendering airmail templates. (can you modify this and does it affect emails when you put stuff here?? @jon) see template rendering

### templates
only html files and directories here.

#### Page Templates
only html. should match those set in modify in admin panel (or they will simply be unused templates and template dirs.). these are for pages. see template rendering

#### Template Directories
template directories should match those set in modify in admin panel (or they will simply be unused templates and template dirs.). these are for collections.
see template rendering
