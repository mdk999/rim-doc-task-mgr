[Home](../../readme.md) > [Schemas](schemas.md) > Users

### User table schema:

----
````mysql
create table `users`
(
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `first_name`  varchar(255)    NOT NULL,
    `last_name`   varchar(255)    NOT NULL,
    `email`       varchar(255)    DEFAULT NULL,
    `password`    varchar(200)    DEFAULT NOT NULL,
    `remember_me` varchar(200)    DEFAULT NULL,
    `is_api_user` tinyint(1)      NOT NULL DEFAULT '0',
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    `disabled`    tinyint         NOT NULL DEFAULT '0',
    PRIMARY KEY (`id`)
)
    
````
[API](../api/user.md)
