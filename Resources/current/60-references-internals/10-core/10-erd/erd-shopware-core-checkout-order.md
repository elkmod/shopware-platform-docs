# erd-shopware-core-checkout-order

[Back to modules](../10-modules.md)

Order management of Shopware 6. Notice: The data structure in this module is mostly decoupled from the rest of the system so deleting customers, products and other entities will not break already placed orders.

![Orders](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-checkout-order.png)

## Table `order`

The root table of the order process. Contains the basic information related to an order and relates to a more detailed model representing the different use cases.

## Table `order_address`

Stores the specific addresses related to the order. Denormalized so a deleted address does not invalidate the order.

## Table `order_customer`

Teh customer related to the order. Denormalized so a deleted customer does not invalidate the order.

## Table `order_delivery`

Represents an orders delivery information and state. Realizes the concrete settings with which the order was created in the checkout process.

## Table `order_delivery_position`

Relates the line items of the order to a delivery. This represents multiple shippings per order.

## Table `order_line_item`

A line item in general is an item that was ordered in a checkout process. It can be a product, a voucher or whatever the system and its plugins provide. They are part of an order and can be related to a delivery and is related to order.

## Table `order_transaction`

A concrete possibly partial payment for a given order. Is always related to a payment method and the state machine responsible for the process management.

[Back to modules](../10-modules.md)

