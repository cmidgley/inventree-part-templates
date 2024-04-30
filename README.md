# InvenTree Template Pro

This plugin extends InvenTree Templates Pro to enhance the clarity and professionalism of your reports
and labels. Key features include:

- Contextual Templates: Define templates associated with specific categories and parts. This allows
your reports to utilize parameters that are most relevant to each part, ensuring that the
information is both precise and contextually appropriate.  
- Detailed Object Interaction: Display and interact with detailed information about InvenTree
objects. This feature enables you to explore properties and methods essential for assembling the
information your report requires.  
- Enhanced Tagging and Filtering: Utilize helper filters and tags that offer advanced capabilities.
For example, you can contextually filter (scrub) content to clean up imported parameter values.
Additionally, it is possible to call methods on objects with specific parameters, providing deeper
access to InvenTree models.

## Context templates

Display contextual information about parts based on new category templates. For example, instead of having descriptions from the vendors such as these:

<table><tr><td>
<img alt="C25076 | 0402WGF1000TCE"
src="https://github.com/cmidgley/inventree-template-pro/raw/main/README-images/default-label-example.png"
style="border: black 1px solid" width="200px"></td>
<td><img alt="0402WGF1000TCE Passives / Resistors 62.5mW 100Ω 50V Thick Film Resistors ±200ppm/℃ ±1% 0402 Chip Resistor - Surface Mount ROHS"
src="https://github.com/cmidgley/inventree-template-pro/raw/main/README-images/detailed-label-example.png"
style="border: black 1px solid" width="200px"></td>
</tr>
</table>

You can instead have properties that are specific to your part, such as showing resistance and wattage parameters for your resistors, and showing capacitance and max voltage for your capacitors:

<img alt="100ohm 62.5mw 1% SMD 0402" src="https://github.com/cmidgley/inventree-template-pro/raw/main/README-images/29mm-label-example.png" style="border: black 1px
solid" width="200px">

## Parameter Scrubbing

Parameters on parts are convenient, but often inconsistent, especially when automatically importing
parts and parameters from suppliers such as DigiKey, Mouser, and LCSC. For example, a parameter of
"Mounting Type" might be listed as "SMT", "SMD", "Surface Mount", or even "[Brick
Nogging](https://www.eevblog.com/forum/chat/where-does-all-the-weird-chinese-component-terminology-come-from/msg4313581/#msg4313581)"!

Parameter scrubbing is a way to cleanse properties using [Regular
Expressions](https://en.wikipedia.org/wiki/Regular_expression).  The cleansing does not change the
property value in the database, so there is no risk of accidental loss of information by scrubbing.
It is used only to resolve templates for labels/reports and only when you use the new `item` or
`scrub` filters.

For example, the scrubbing can make the following adjustments (contextual to the property type):

- "10VDC (at 40C)" -> "10V"
- "Brick Nogging" -> "SMT"
- "1.2 uF (1200 nF)" -> "1.2µF"


## Object Exploring

InvenTree is quite powerful with a well-designed object model, including plenty of properties and access
methods make detailed, high-quality reports. The challenge is finding the information to make those
reports. You can spend hours searching the source and guessing at property and method names, or
simply use this tag:

```django
{% explore Part style="interactive" %}
```

Your report will contain detailed information about the members of the part, like this (shown with
the "interactive" style using reports in debug mode for HTML interaction):

<img alt="Screen shot of Explore tag with the Interactive style" src="https://github.com/cmidgley/inventree-template-pro/raw/main/README-images/explore-interactive-example.png" style="border: black 1px
solid" width="350px">

## Example Labels and Reports

A few example labels and reports are provided (the ones the author uses) to show how to use these
capabilities. For example, here is a fragment of a "Build report" that contains detailed part
information including stock allocation details:

<img alt="Partial example build report" src="https://github.com/cmidgley/inventree-template-pro/raw/main/README-images/build-report-example.png" style="border: black 1px
solid" width="350px">


## Documentation

General documentation on installation, configuration, and usage:

- [Installation](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/installation.md): Brief description of how to install the plugin.
- [Context Templates](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/context-templates.md): How to use Context Templates for parts based on part categories.
- [Parameter Scrubbing](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/parameter-scrubbing.md): How to configure parameter scrubbing to clean up imported parameter values.
- [Example reports](https://github.com/cmidgley/inventree-template-pro/tree/main/example_reports) and [Example labels](https://github.com/cmidgley/inventree-template-pro/tree/main/example_labels): Review examples included in this GitHub repo.

Information on each of the tags and filters provided by InvenTree Template Pro:

- [`call` tag](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/call-tag.md): Utility tag to call any method of an object with parameters.
- [`explore` tag](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/explore-tag.md): Explore the properties and methods of InvenTree objects in your reports.
- [`item` filter](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/item-filter.md): Retrieve a property value from a part (or any dictionary) with automatic Parameter Scrubbing.
- [`part_context` tag](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/part-context-tag.md): Get a part context using Context Templates for any part, such as when
  processing parts in a loop for reporting.
- [`replace` filter](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/replace-filter.md): Helper method to replace content in a string using simple match/replace or
  more advanced with regular expressions.
- [`scrub` filter](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/scrub-filter.md): Scrub any string based on any filter name using Parameter Scrubbing.
- [`value` filter](https://github.com/cmidgley/inventree-template-pro/tree/main/README-images/value-filter.md): Retrieve a property value from a part (or any dictionary), without Parameter Scrubbing.

## License

Licensed under the [MIT License](https://github.com/cmidgley/inventree-template-pro/tree/main/LICENSE).