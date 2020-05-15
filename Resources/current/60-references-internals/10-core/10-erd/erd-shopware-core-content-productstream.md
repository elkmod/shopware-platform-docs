# erd-shopware-core-content-productstream

[Back to modules](../10-modules.md)

Product streams describe stored filter conditions that applied to the catalogue as a whole to create dynamic streams.

![Product streams](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-content-productstream.png)

## Table `product_stream`

Product streams are a dynamic collection of products based on stored search filters. This is the root table representing these filters. _Attention: after creation, product streams need to be indexed, they can not be used until `invalid` is `false`_

## Table `product_stream_filter`

Represents a single filter property. All to a stream related filters build a persisted and nested search query.

[Back to modules](../10-modules.md)

