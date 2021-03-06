# erd-shopware-core-system-numberrange

[Back to modules](../10-modules.md)

Numberranges are used to provide and generate non random but unique numbers for a variety of entities. For example the default stock keeping units \(SKU\) are generated here.

![Number ranges](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-system-numberrange.png)

## Table `number_range`

Is the definition of a number range. The optional sales channel relation acts as a filter here.

## Table `number_range_state`

Represents the current state of a number range by storing the last value.

## Table `number_range_type`

A list of available types, that may be global or lead to associated number ranges.

[Back to modules](../10-modules.md)

