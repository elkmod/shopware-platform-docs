# \_\_categoryInfo

_It is highly recommended to - first - read the_ [_cart documentation_](../50-checkout-process/10-cart.md)

The rule system pervades Shopware 6. It solves the problem of calculating the cart differently based on the context \(`SalesChannel`, `CustomerGroup`, `...`\) and the current state \(`LineItems`, `Amount`, `...`\), but user controlled and decoupled from the cart itself. In theory [every part of Shopware 6](10-rule-list.md) can contribute to the set of available rules.

## Scenario

The problem solved by the rule system can be imagined by the following scenario:

> If a customer orders a car, a pair of sunglasses in the same order will be free.

This carelessly uttered sentence relies on the knowledge of multiple different data points:

* A product called _car_
* A product called _sunglasses_

Both independent and separately buyable. Stored to the database.

* The whole state of a single cart
* The quantity of a line item

A runtime concept - in memory.

Resulting in the adjustment of a single line items price, which in turn changes the whole **calculation of the cart**.

In this example the rule system sits right in the middle of the scenario, providing the necessary mapping information to get from _point a_ \(`car` is in the cart\) to _point b_ \(`sunglasses` are free\).

## Rule Design

The center of the rule system is the [`Rule`](https://github.com/shopware/platform/blob/master/src/Core/Framework/Rule/Rule.php), it is realized as a variant of the [Specification pattern](https://en.wikipedia.org/wiki/Specification_pattern), but omits the name due to a few key differences.

* _Storable_ and _retrievable_ and **identifiable** through the [Data Abstraction Layer](../10-erd/erd-shopware-core-content-rule.md)
* A `RuleScope` parameter instead of any arbitrary object
* `match` instead of `isSatisfiedBy`

As well as a _Specification class_, a _Rule class_ represents a condition to fulfill. It implements the `match(RuleScope $scope)` function to validate _user defined values_ against a _runtime state_. See the following object diagram for a better understanding:

![rule objects](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/60-rule-system/dist/rule-objects.png)

Which will result in the following call order:

![rule state diagramm](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/60-rule-system/dist/rule-sequence.png)

As you can see a single rule can either contain user defined values or other, user defined, rules. These are _Container rules_. The rule system here bears some resemblance to the [SearchCriteria](../130-dal.md), although independent. Where a criteria is the the representation of a query that gets translated and executed through the storage engine, the rule matches **in memory** in PHP.

The last building block then is the **Rule Scope**. The Scope contains the current runtime state of the application and is necessary to match the data. The whole picture is visualized in the next diagram:

![rule classes](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/60-rule-system/dist/rule-classes.png)

## Connection to the System

Following Shopware 6s data driven approach the rule objects are stored to the [database](../10-erd/erd-shopware-core-content-rule.md) and used to trigger behaviour in the cart through the associations present.

For more insights on the rule validation take a look at the [cart documentation](../50-checkout-process/10-cart.md)

