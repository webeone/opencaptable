This page is to capture future _breaking changes_ that we would like to make to complete / clean-up non-breaking changes made under 1.x. Rather than clutter the issue tracker with these items that may not be addressed for a very long time, we will capture them here.

This is also a useful guide for developers to see 1.x concepts that may be deprecated, and how to avoid these items.

### Remove `conversion_timing` from `SAFEConversionMechanism`

[#401](https://github.com/Open-Cap-Table-Coalition/Open-Cap-Format-OCF/pull/401) added an improved method for representing capitalization definitions. We believe `conversion_timing` is no longer necessary with that representation, and could potentially conflict with it if both are present.
