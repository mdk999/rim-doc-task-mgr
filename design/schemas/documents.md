[Home](../../readme.md) > [Schemas](schemas.md) > Document

### Documents table schema:

----
````mysql
create table `documents`
(
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `name`  varchar(255)    NOT NULL,
    `filename`   varchar(255)    NOT NULL,
    `hash`       varchar(255)    DEFAULT NULL,
    `version`    bigint,
    `user_id`    bigint,
    `size`       int,
    `status`    enum('pending','completed','failed'),
    `mime` varchar(255)    DEFAULT NULL,
    `ext` varchar(255)    DEFAULT NULL,
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    `private`    tinyint         NOT NULL DEFAULT '0',
    `parent_document`    bigint,
    PRIMARY KEY (`id`),
    FULLTEXT KEY (`name`),
    KEY `documents_user_id_foreign` (`user_id`),
    CONSTRAINT `documents_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)
)
    
````
[API](../api/document.md)
