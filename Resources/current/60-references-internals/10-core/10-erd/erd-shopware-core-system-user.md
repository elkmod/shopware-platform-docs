# erd-shopware-core-system-user

[Back to modules](../10-modules.md)

Account management of administration users.

![Admin Accounts](https://github.com/elkmod/shopware-dx/tree/0c4bd450b25734a607955d03e7f7a908abf1a386/Resources/current/60-references-internals/10-core/10-erd/dist/erd-shopware-core-system-user.png)

## Table `user`

Stores account details associated with an administration user.

## Table `user_access_key`

Stores the oAuth access for a specific account to the admin.

## Table `user_recovery`

Simple M:N association related to the password recovery process.

[Back to modules](../10-modules.md)

