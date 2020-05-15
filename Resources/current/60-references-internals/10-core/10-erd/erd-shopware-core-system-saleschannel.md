# erd-shopware-core-system-saleschannel

[Back to modules](../10-modules.md)

The sales channels provide access to all typical frontend related content. A sales channel provides managed and controlled access to the product catalogue or the checkout process. Contrary to admin access, sales channel access is bound to concrete and strict processes. The specific domain logic of Shopware.

![Sales channels](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-system-saleschannel.png)

## Table `sales_channel`

The root entity for all sales channel related structures. Provides the means for api authentication, default configuration and acts as a filter for published data to a sales channel.

## Table `sales_channel_domain`

List of domains under which the sales channel is reachable.

## Table `sales_channel_type`

Modifies the sales channel behaviour.

[Back to modules](../10-modules.md)

