# erd-shopware-core-content-product

[Back to modules](../10-modules.md)

Central product representation. Contains products and variations based on configuration.

![Products](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-content-product.png)

## Table `product`

A rich domain model representing single products or its variants. This is done through relations, so a root product is related to its variants through a foreign key.

## Table `product_configurator_setting`

Association from a root product to a configuration set. Used to generate variants and surcharge or discount the price.

## Table `product_price`

Different product prices based on rules.

## Table `product_search_keyword`

SQL based product search table, containing the keywords.

## Table `product_keyword_dictionary`

SQL based product search table containing the dictionary.

## Table `product_review`

**EMPTY**

## Table `product_manufacturer`

The product manufacturer list.

## Table `product_media`

Relates products to media items, usually images.

## Table `product_visibility`

Set the visibility of a single product in a sales channel

[Back to modules](../10-modules.md)

