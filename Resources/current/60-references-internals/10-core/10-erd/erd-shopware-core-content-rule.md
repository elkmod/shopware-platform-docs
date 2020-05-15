# erd-shopware-core-content-rule

[Back to modules](../10-modules.md)

Rules are used throughout Shopware 6 to provide dynamic decision management. For instance shipping and billing methods are matched to customers, carts and line items based on rules from these resources.

![Rules](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-content-rule.png)

## Table `rule`

A rule is the collection of a complex set of conditions, that can be used to influence multiple workflows of the order process.

## Table `rule_condition`

Each row is related to a rule and represents a single part of the query the rule needs for validation.

[Back to modules](../10-modules.md)

