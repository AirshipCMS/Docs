# Propeller Helpers
While these helpers are not available in the [layout](Layouts.md) level, they are available in all template files such as [page](Page-Templates.md) or [collection](Collection-Templates.md) templates.

A propeller helper is an expression wrapped in curly braces, such as `{{format_date}}`.

When using these helpers within nested context, such as when rendering [image](Datafields.md#field-type-image) or [link](Datafields.md#field-type-link) fields, the syntax has a `#` preceeding the expression. See [#each](HandlebarsJS.md#each), or [#sort_list](#sort_list) for examples. 

Check out the [HandlebarsJS](HandlebarsJS.md) documentation for more helpers.


## {{{help}}}
Add `{{{help}}}` to any of the template files to see which properties and fields are available for that page. All available properties and fields render as a bulleted list. Items in collections must be published in order to be accessible.

This does not render in production.

Variable names with `[list]` indicate that the field is an array of items. These fields require either the [#each](HandlebarsJS.md#each) or [#sort_list](#sort_list) propellers.

Any desired properties or fields that are not listed when rendering help must be accessed via API calls or other methods.


## {{format_date}}
This helper is for formatting both UNIX and UTC timestamps, and expects the following syntax:
```
{{format_date VARIABLE_NAME "STRING_PATTERN" "LOCALE"}}
```

`STRING_PATTERN` is a string that can be a custom strftime/MS or a builtin pre-format string.

Example string patterns:
```
April 16, 2016 // "%B %d, %Y"
April 16, 2016 10:00am // "%B %d, %Y %l:%M%P"
4/16/2016 // “d” or "%m/%d/%Y"
4/16/2016 10:00am // "%m/%d/%Y %l:%M%P"
```

Here are the available options for `LOCALE`:
```
au, ie, gb, us, jp
```

Full Example Markup and Output:
```
{{ format_date published_at "D" "jp" }} => 2016年5月27日
```

Built In Patterns:
```
NO PATTERN: May 27, 2016
PATTERN (d): 05/27/2016
PATTERN (D): 2016年5月27日
PATTERN (f): Friday, 27 May 2016 06:14
PATTERN (F): Friday, 27 May 2016 06:14:04
PATTERN (g): 05/27/2016 06:14
PATTERN (G): 05/27/2016 06:14:04
PATTERN (m): May 27
PATTERN (M): May 27
PATTERN (o): 2016-05-27T06:14:04.1650000+00:00
PATTERN (O): 2016-05-27T06:14:04.1650000+00:00
PATTERN (r): Fri, 27 May 2016 06:14:04 GMT
PATTERN (R): 05/27/2016 06:14:04
PATTERN (s): 2016-05-27T06:14:04
PATTERN (t): 06:14
PATTERN (T): 06:14:04
PATTERN (u): 2016-05-27 06:14:04Z
PATTERN (U): Friday, 27 May 2016 06:14:04
PATTERN : 2016 May
PATTERN (Y): 2016 May
PATTERN (ddd yyyy): Fri 2016
PATTERN (MMM): May
PATTERN (%B %d, %Y %l:%M%P): May 27, 2016 6:14am
PATTERN (%m/%d/%Y %l:%M%P): 05/27/2016 6:14am
```

Refer to http://thx-lib.org/lib/thx.format/ for more information.


## {{format_currency}}
This helper is used to format any content entered in Admin as currency.

There are currently two formatting options for US Dollars.

Example Markup:
```
<p>{{price.usd}}</p>
<p>{{format_currency this.price "usd"}}</p>
<p>{{format_currency this.price "usd" 2}}</p>
```

Example Output:
```
<p>500</p>
<p>$5</p>
<p>$5.00</p>
```

## {{create_page_query}}

This helper is for pagination and uses the `params` property listed when rendering `{{{help}}}`.

The `params` fields can be combined to create query strings that specify the page number, item limit, sort options, and other info used to traverse through pages.

The following is a list of all possible fields on the `params` property and how to access them, followed by example usages:
```
page: {{params.page}}  // The current page number
limit: {{params.limit}}  // The amount of items that can be displayed at a time
offset: {{params.offset}}  // The current interval of items being displayed (limit*(page-1))
sort: {{params.sort}}  // The field to sort by, e.g. permalink or id
order: {{params.order}}  // Either asc (ascending) or desc (descending) order
total_count: {{params.total_count}}  // The total amount of items
page_count: {{params.page_count}}  // The total amount of pages required to render all items
next_offset: {{params.next_offset}}  // The next interval of items to render
prev_offset: {{params.prev_offset}}  // The previous interval of items to render
next_page: {{params.next_page}}  // The next page number
prev_page: {{params.prev_page}}  // The previous page number
fetch_first: {{params.fetch_first}}  // The query string for the first page
fetch_last: {{params.fetch_last}}  // The query string for the last page
fetch_prev: {{params.fetch_prev}}  // The query string for the previous page
fetch_next: {{params.fetch_next}}  // The query string for the next page
fetch_first_offset: {{params.fetch_first_offset}}  // The query string for the first offset
fetch_last_offset: {{params.fetch_last_offset}}  // The query string for the last offset
fetch_prev_offset: {{params.fetch_prev_offset}}  // The query string for the previous offset
fetch_next_offset: {{params.fetch_next_offset}}  // The query string for the next offset
```

### Using `{{create_page_query}}` with no options
If not specified, the following are the default parameters for `{{create_page_query}}`:
```
page: 1,
limit: 50,
sort: id,
order: asc
```

Example Markup:
```
<li><a href="mammals{{create_page_query}}">Mammals</a></li>
```

Example Output:
```
<li><a href="mammals?page=1&amp;limit=50&amp;sort=id&amp;order=asc">Mammals</a></li>
```

### Using `{{create_page_query}}` with `sort`, `order`, and `limit`
Example Markup:
```
<li><a href="{{create_page_query sort='permalink' order='asc' limit='15'}}">Mammals</a></li>
```

Note: There is no need to specify the collection name if used within the collection's public path namespace.

Example Output:
```
<li><a href="?page=1&amp;limit=15&amp;sort=permalink&amp;order=asc">Mammals</a></li>
```

### Traversing through pages using `params` fields
The params fields will use default values unless any were specified.

Note how `order` is `asc` in the following example output without specifying it in the markup.

Example Markup:
```
<li><a href="{{collection.public_path}}?page=3&limit={{params.limit}}&sort={{params.sort}}&order={{params.order}}">Page 3</a></li>
```

Example Output:
```
<li><a href="mammals?page=3&amp;limit=15&amp;sort=permalink&amp;order=asc">Page 3</a></li>
```

### Traversing through pages using the `params` `fetch` fields
Links can be created to traverse through the pages by either page numbers, or offset intervals.

Example Markup:
```
<li><a href="{{params.fetch_first}}">Fetch First</a></li>
<li><a href="{{params.fetch_last}}">Fetch Last</a></li>
<li><a href="{{params.fetch_prev}}">Fetch Prev</a></li>
<li><a href="{{params.fetch_next}}">Fetch Next</a></li>
<li><a href="{{params.fetch_first_offset}}">Fetch First Offset</a></li>
<li><a href="{{params.fetch_last_offset}}">Fetch Last Offset</a></li>
<li><a href="{{params.fetch_next_offset}}">Fetch Next Offset</a></li>
<li><a href="{{params.fetch_prev_offset}}">Fetch Prev Offset</a></li>
```

Example Output from the first page of a `/collection/index.html`, with `limit=15` and `sort=permalink`:
```
<li><a href="?page=1&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch First</a></li>
<li><a href="?page=4&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Last</a></li>
<li><a href="?page=1&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Prev</a></li>
<li><a href="?page=2&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Next</a></li>
<li><a href="?offset=0&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch First Offset</a></li>
<li><a href="?offset=45&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Last Offset</a></li>
<li><a href="?offset=15&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Next Offset</a></li>
<li><a href="?offset=0&amp;limit=15&amp;sort=permalink&amp;order=asc">Fetch Prev Offset</a></li>
```

## {{#sort_list}}
This is used to sort items in lists. It is used in place of the [#each](HandlebarsJS.md#each) helper.

When using this helper, you can set the list to sort by any "first level" alphabetical or date properties such as [permalink](Properties.md#permalink), [public path](Properties.md#public-path), [published_on](Properties.md#published-on) or [created_at](Properties.md#created-at). Currently, it is not possible to use any nested properties for sorting, such as those in `fields`. Use the [help propeller](#help) to check for available first level properties.

The syntax is as follows:
```
{{#sort_list array sort="property" order="asc"}} 
  <!--fields and markup--> 
{{/sort_list}}
```

Where `array` is the list of items

Where `property` is any property available on the items.

Where `order` is either `asc` or `desc`

Example on the index.html template of a collection, sorting all items by their sorting position, in ascending order:
```
{{#sort_list items sort="sorting_position" order="asc"}}
  <a href="{{slug}}">{{fields.name}}</a>
{{/sort_list}}
```

Example Output:
```
<a href="/mammals/view/hedgehog">hedgehog</a>
<a href="/mammals/view/rabbit">rabbit</a>
<a href="/mammals/view/cheetah">cheetah</a>
```
