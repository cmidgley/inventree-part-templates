
<p align="center"><img src="images/InvenTree Template Pro Logo.png" alt="InvenTree Template Pro
Logo" width="80px"></p>

<h3 align="center">

[InvenTree Template Pro](README.md)

</h3>


#### Installation, configuration, and usage:

- [Installation](installation.md): Brief description of how to install the plugin.
- [Context Templates](context-templates.md): How to use Context Templates for parts based on part categories.
- [Parameter Scrubbing](parameter-scrubbing.md): How to configure parameter scrubbing to clean up imported parameter values.
- [Example reports](../inventree_template_pro/examples/reports) and [Example labels](../inventree_template_pro/examples/labels): Review examples included in this GitHub repo.

#### Tags and filters

- [`call` tag](tags/call.md): Utility tag to call any method of an object with parameters.
- [`explore` tag](tags/explore.md): Explore the properties and methods of InvenTree objects in your reports.
- [`item` filter](filters/item.md): Retrieve a property value from a part (or any dictionary) with automatic Parameter Scrubbing.
- [`part_context` tag](tags/part-context.md): Get a part context using Context Templates for any part, such as when
  processing parts in a loop for reporting.
- [`replace` filter](filters/replace.md): Helper method to replace content in a string using simple match/replace or
  more advanced with regular expressions.
- [`scrub` filter](filters/scrub.md): Scrub any string based on any filter name using Parameter Scrubbing.
- [`value` filter](filters/value.md): Retrieve a property value from a part (or any dictionary), without Parameter Scrubbing.