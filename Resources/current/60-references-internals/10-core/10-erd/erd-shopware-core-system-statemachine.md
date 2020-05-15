# erd-shopware-core-system-statemachine

[Back to modules](../10-modules.md)

Like the rule system, that makes core decisions configurable through the Rest-API, the state machine makes core workflows configurable. State machines in checkout, payment and delivery processing are used to adapt Shopware 6 to custom needs.

![State machine](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-system-statemachine.png)

## Table `state_machine`

The central entity for state management in Shopware. Allows you to create custom workflows for order, delivery und payment management.

## Table `state_machine_state`

A possible state for a related state machine.

## Table `state_machine_transition`

A transition connects two states with each other and calls an action on transition.

## Table `state_machine_history`

The concrete transition history of a given context \(namely `entityName`, `entityId`\).

[Back to modules](../10-modules.md)

