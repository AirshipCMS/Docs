# Docs for AirshipCMS.io.
This documentation is for airshipcms.io. You can also view it, along with additional illustrations and better navigation, at [airshipcms.io/documentation/view/introduction](https://airshipcms.io/documentation/view/introduction).

---

- [Introduction-to-Airship.md](/Introduction-to-Airship.md)
- [Quickstart-Guide.md](/Quickstart-Guide.md)
- [Schema-Setup-Guide.md](/Schema-Setup-Guide.md)
- [Development-Guide.md](/Development-Guide.md)
- [Project-Directory.md](/Project-Directory.md)
- [Boilerplates-and-Examples.md](/Boilerplates-and-Examples.md)
- [How-Airship-CLI-Works.md](/How-Airship-CLI-Works.md)
- [Install-Airship-CLI-Tools.md](/Install-Airship-CLI-Tools.md)
- [Airship-CLI-Commands.md](/Airship-CLI-Commands.md)
- [Airship-CLI-Troubleshooting.md](/Airship-CLI-Troubleshooting.md)
- [Using-Layouts-and-Templates.md](/Using-Layouts-and-Templates.md)
- [Layouts.md](/Layouts.md)
- [Page-Templates.md ](/Page-Templates.md )
- [Collection-Templates.md](/Collection-Templates.md)
- [Collection-Index-Template.md](/Collection-Index-Template.md)
- [Collection-Show-Template.md](/Collection-Show-Template.md)
- [Collection-Categories-Template.md](/Collection-Categories-Template.md)
- [Collection-Category-Template.md](/Collection-Category-Template.md)
- [Airmail-Email-Templates.md](/Airmail-Email-Templates.md)
- [Airmail-Public-Make-Template.md](/Airmail-Public-Make-Template.md)
- [Page-Properties.md](/Page-Properties.md)
- [Collection-Item-Properties.md](/Collection-Item-Properties.md)
- [Datafields.md](/Datafields.md)
- [Related-Items.md](/Related-Items.md)
- [Propeller-Helpers.md](/Propeller-Helpers.md)
- [Partials.md](/Partials.md)
- [Content-Blocks.md](/Content-Blocks.md)
- [HandlebarsJS.md](/HandlebarsJS.md)
- [Introduction-to-Airship-API.md](/Introduction-to-Airship-API.md)
- [Introduction-to-Airship-CMS.md](/Introduction-to-Airship-CMS.md)
- [Schema-and-Data-Model.md](/Schema-and-Data-Model.md)
- [Pages.md](/Pages.md)
- [Collections.md](/Collections.md)
- [Categories.md](/Categories.md)
- [Relationships.md](/Relationships.md)
- [Users.md](/Users.md)
- [Making-Your-Site-Live.md](/Making-Your-Site-Live.md)


### Adding to examples to /properties
Conventions for /properties examples:

If a property is specific to a certain template, notate it as `[template--property_name]`, e.g. `[categories--has_categories]`

Properties notated as `single` or `each` are general exapmles that are usable among various templates.

When creating in AirshipCMS:

the field `notation` should be just the notations listed in repo pages, e.g. `[categories--has_categories]`

the `permalink` should match the notation

the `property_name` should be just the property name, without the notation, e.g. `has_categories`
