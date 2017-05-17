# Layouts
A layout is the shell... Layouts are located in...
The filename should match what is set in the Modify of the page or collection...

A layout is set for a page, or for all views in a collection. (cannot yet set different layouts for different templates in a collection).

## Layout Built-in Server-side Rendering with Propellers:
- ??not sure. list

## No Server-side Rendering for these properties:
- You don't have access to properties properties for specific pages/collections. this is problematic when there is dynamic content that needs to be rendered in the <head> for a collection. if this is the case, you will need to forego using the layout for rendering, and instead put the entire head content in the template for collection... :P
