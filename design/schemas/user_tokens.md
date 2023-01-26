[Home](../../readme.md) > [Schemas](schemas.md) > UserTokens

### UserTokens table schema:

----
````mysql
create table `user_tokens`
(
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `id_token`       varchar(255),
    `access_token`       varchar(255),
    `refresh_token`       varchar(255),
    `name`       varchar(255),
    `token_type`       varchar(200),
    `user_id`    bigint,
    `abilities`   text,
    `expires_in`   int,
    `last_used_at`  timestamp       NULL     DEFAULT NULL,
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    PRIMARY KEY (`id`),
    KEY `access_tokens_user_id` (`user_id`),
    CONSTRAINT `access_tokens_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)
)
    
````
