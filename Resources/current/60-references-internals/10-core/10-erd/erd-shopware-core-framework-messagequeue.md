# erd-shopware-core-framework-messagequeue

[Back to modules](../10-modules.md)

The message queue provides the necessary glue code between the API and the internally used message bus.

![Asynchronous messaging](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-framework-messagequeue.png)

## Table `dead_message`

Failing messages in the queue. Requeued with an ever increasing threshold.

## Table `message_queue_stats`

The number of tasks currently in the queue.

[Back to modules](../10-modules.md)

