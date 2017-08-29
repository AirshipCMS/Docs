Layouts are the base HTML markup that is shared across templates that use the same layout.

## Layout Properties
The only property that the layout has access to is the `template`. The template property tells the layout which template file it should be rendering.

In order to render templates from a layout file, add `{{{template}}}` anywhere between the `body` tags of the layouts HTML file. You can set which template files will render through which layouts by modifying the page or collection in the Admin portal.

## Properties you can't access from a layout
Layouts do not have access to any page, aerostat, or collection properties. To find out more about how to start accessing these properties, check out the documentation on [page](https://airshipcms.io/documentation/view/page-templates) or [collection](https://airshipcms.io/documentation/view/collection-templates) templates.

Layouts are helpful to use as template shells that contain the same information across various pages, such as headers, footers, or script tags.

For example, if your site has multiple pages that have the same banner area, you can include the markup for the banner area _once_ in the layout that each template is configured to use. The banner will now render on each of those pages without having to rewrite the markup in each template.

If your site has content that is repetitive across different layouts and templates, such as navigation bars or footers, you can use Airship partials to avoid having to repeat HTML markup in each file. Check out the [partials](https://airshipcms.io/documentation/view/partials) documentation for more information on how and where you can use them.
