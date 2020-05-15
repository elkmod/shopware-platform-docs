# 10-modules

All core modules encapsulate domain concepts and provide a varying number of external interfaces to support this. The following list provides a rough overview what domain concepts offer what kinds of interfaces.

## Possible characteristics

Data store : These modules are related to database tables and are manageable through the API. Simple CRUD actions will be available.

Maintenance : Provide commands executable through CLI to trigger maintenance tasks.

Custom actions : These modules contain more than simple CRUD actions. They provide special actions and services that ease management and additionally check consistency.

SalesChannel-API : These modules provide logic through a sales channel for the storefront.

Custom Extendable : These modules contain interfaces, process container tags or provide custom events as extension points.

Business Event Dispatcher : Provide special events to handle business cases.

Extension : These modules contain extensions of - usually Framework - interfaces and classes to provide more specific functions for Shopware 6.

Custom Rules : Cross-system process to validate workflow decisions.

## Modules

### Checkout Bundle

#### Cart Custom actions Custom Extendable Business Event Dispatcher Extension Custom Rules

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Cart) 

Cart processes

#### Customer Data store Custom Extendable Business Event Dispatcher Extension Custom Rules

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Customer) 

SalesChannel Customer

* [Entity relationship diagram](10-erd/erd-shopware-core-checkout-customer.md)

#### Order Data store Custom actions Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Order) 

Order management

* [Entity relationship diagram](10-erd/erd-shopware-core-checkout-order.md)

#### Payment Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Payment) 

Payment methods

* [Entity relationship diagram](10-erd/erd-shopware-core-checkout-payment.md)

#### Promotion Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Promotion) 

Promotions

* [Entity relationship diagram](10-erd/erd-shopware-core-checkout-promotion.md)

#### Shipping Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Checkout/Shipping) 

Shipping methods

### Content Bundle

#### Category Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Category) 

Product Categories

* [Entity relationship diagram](10-erd/erd-shopware-core-content-category.md)

#### Cms Data store Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Cms) 

Content Management System

#### DeliveryTime Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/DeliveryTime) 

Delivery time

* [Entity relationship diagram](10-erd/erd-shopware-core-content-deliverytime.md)

#### ImportExport Data store Maintenance Custom actions Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/ImportExport) 

Mass imports and exports through files

* [Entity relationship diagram](10-erd/erd-shopware-core-content-importexport.md)

#### MailTemplate Data store Custom actions Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/MailTemplate) 

Mailing

* [Entity relationship diagram](10-erd/erd-shopware-core-content-mailtemplate.md)

#### Media Data store Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Media) 

Media/File management

* [Entity relationship diagram](10-erd/erd-shopware-core-content-media.md)

#### Newsletter Data store Custom Extendable Business Event Dispatcher Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Newsletter) 

Newsletter

#### Product Data store Custom actions Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Product) 

Products and Variants

* [Entity relationship diagram](10-erd/erd-shopware-core-content-product.md)

#### ProductStream Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/ProductStream) 

Product Streams

* [Entity relationship diagram](10-erd/erd-shopware-core-content-productstream.md)

#### Property Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Property) 

Content configuration

* [Entity relationship diagram](10-erd/erd-shopware-core-content-property.md)

#### Rule Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Content/Rule) 

Rule Builder

### Framework Bundle

#### Api Maintenance Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Api) 

Rest-API

#### Cache

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Cache) 

Cache helpers

#### Console

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Console) 

Console helpers

#### Context Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Context) 

Main context

#### CustomField Data store Custom actions Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/CustomField) 

Custom field management

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-customfield.md)

#### DataAbstractionLayer Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/DataAbstractionLayer) 

Data Abstraction Layer - the central component responsible for all storage access.

* [user guide](130-dal.md)

#### Doctrine

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Doctrine) 

Doctrine DBAL extension

#### Event Data store Custom Extendable Business Event Dispatcher Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Event) 

Business events

#### FeatureFlag Maintenance

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/FeatureFlag) 

Feature Flag configuration

#### Filesystem Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Filesystem) 

Filesystem handling

#### Language Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Language) 

Languages

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-language.md)

#### Log

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Log) 

Logging

#### MessageQueue Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/MessageQueue) 

Async processing

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-messagequeue.md)
* [Guide](00-module/message-queue.md)

#### Migration Maintenance Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Migration) 

Database migration system

#### Plugin Data store Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Plugin) 

Plugin services

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-plugin.md)

#### Pricing Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Pricing) 

Pricing

#### Routing Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Routing) 

Routing

#### Rule Custom Extendable Extension Custom Rules

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Rule) 

Rule matching

#### ScheduledTask Data store Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/ScheduledTask) 

Cron jobs

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-scheduledtask.md)
* [Guide](00-module/scheduled-tasks.md)

#### Snippet Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Snippet) 

Translation management

* [Entity relationship diagram](10-erd/erd-shopware-core-framework-snippet.md)

#### Store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Store) 

Plugin store

#### Struct Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Struct) 

Structured data

#### Translation

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Translation) 

Abstract translations

#### Twig

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Twig) 

Template extension

#### Uuid

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Uuid) 

UUID Handling

#### Validation Custom Extendable

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/Framework/Validation) 

Validation

### System Bundle

#### Country Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Country) 

Countries

* [Entity relationship diagram](10-erd/erd-shopware-core-system-country.md)

#### Currency Data store Extension Custom Rules

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Currency) 

Currencies

* [Entity relationship diagram](10-erd/erd-shopware-core-system-currency.md)

#### Integration Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Integration) 

Admin integrations

* [Entity relationship diagram](10-erd/erd-shopware-core-system-integration.md)

#### Locale Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Locale) 

Locales

* [Entity relationship diagram](10-erd/erd-shopware-core-system-locale.md)

#### NumberRange Data store Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/NumberRange) 

Number ranges \(SKU\)

* [Entity relationship diagram](10-erd/erd-shopware-core-system-numberrange.md)
* [Guide](00-module/number-range.md)

#### SalesChannel Data store Maintenance Custom Extendable Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/SalesChannel) 

Sales Channels

* [Entity relationship diagram](10-erd/erd-shopware-core-system-saleschannel.md)

#### Salutation Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Salutation) 

Salutation

* [Entity relationship diagram](10-erd/erd-shopware-core-system-salutation.md)

#### StateMachine Data store Maintenance Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/StateMachine) 

Order state management

* [Entity relationship diagram](10-erd/erd-shopware-core-system-statemachine.md)

#### SystemConfig Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/SystemConfig) 

Shopware 6 Configuration

* [Entity relationship diagram](10-erd/erd-shopware-core-system-systemconfig.md)

#### Tag Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Tag) 

Content Tagging

#### Tax Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Tax) 

Taxes

* [Entity relationship diagram](10-erd/erd-shopware-core-system-tax.md)

#### Unit Data store Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/Unit) 

Product / Shipping Units

* [Entity relationship diagram](10-erd/erd-shopware-core-system-unit.md)

#### User Data store Maintenance Extension

* [Sources](https://github.com/shopware/platform/tree/master/src/Core/System/User) 

Admin Users

* [Entity relationship diagram](10-erd/erd-shopware-core-system-user.md)

