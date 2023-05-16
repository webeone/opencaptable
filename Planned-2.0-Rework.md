This page is to capture future _breaking changes_ that we would like to make to complete / clean-up non-breaking changes made under 1.x. Rather than clutter the issue tracker with these items that may not be addressed for a very long time, we will capture them here.

This is also a useful guide for developers to see 1.x concepts that may be deprecated, and how to avoid these items.

### Remove `conversion_timing` from `SAFEConversionMechanism`

[#401](https://github.com/Open-Cap-Table-Coalition/Open-Cap-Format-OCF/pull/401) added an improved method for representing capitalization definitions. We believe `conversion_timing` is no longer necessary with that representation, and could potentially conflict with it if both are present.

### Don't allow `converts_to_stock_class_id` and `converts_to_future_round: true` on the same conversion right
https://github.com/Open-Cap-Table-Coalition/Open-Cap-Format-OCF/blob/5848a7e63dc06018031d54bff2e04be39d3af9ec/schema/primitives/types/conversion_rights/ConversionRight.schema.json#L35-L42

Currently the schema allows a stock class ID and `converts_to_future_round: true` on the same conversion right. This doesn't make sense for a single conversion right; if both things are possible they should be on separate conversion rights. However, adding this requirement now would be a breaking change.

We could add a check to a data validator now, and WARN that this will not be possible in v2.
