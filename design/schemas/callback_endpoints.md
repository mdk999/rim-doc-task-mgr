[Home](../../readme.md) > [Schemas](schemas.md) > CallbackEndpoints

### CallbackEndpoints table schema:

----
````mysql
create table `callback_endpoints` 
(
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `name`  varchar(255)    NOT NULL,
    `endpoint`   varchar(255)    DEFAULT NULL,
    `user_id`    bigint,
    `method`    enum('POST','PUT'),
    `mapping` json    DEFAULT NULL,
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    PRIMARY KEY (`id`),
    KEY `callback_endpoints_user_id_foreign` (`user_id`),
    CONSTRAINT `callback_endpoints_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)
)
    
````
[API](../api/callback_endpoints.md)

