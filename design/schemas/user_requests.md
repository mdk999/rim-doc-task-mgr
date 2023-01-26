[Home](../../readme.md) > [Schemas](schemas.md) > UserRequests

### User table schema:

----
````mysql
create table `user_requests` 
(   
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `url`  varchar(255)    NOT NULL,
    `name`  varchar(255)    NOT NULL,
    `method`   enum('GET','PUT','POST','DELETE'),
    `request_token`       varchar(255)    DEFAULT NULL,
    `expected_result`    varchar(255)    DEFAULT NULL,
    `user_id`    bigint,
    `expected_http_code`       int DEFAULT NULL,
    `request_mapping` json    DEFAULT NULL,
    `request_data` json    DEFAULT NULL,
    `retry_amount`       tinyint(1) DEFAULT NULL,
    `disabled`       tinyint(1) DEFAULT NULL,
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    `request_mode` enum('web','api'),
    PRIMARY KEY (`id`),
    KEY `user_requests_user_id_foreign` (`user_id`),
    CONSTRAINT `user_requests_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)
)
    
````

````mysql
create table `user_request_logs` 
(   
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `user_request_id`    bigint,
    `response_payload` json    DEFAULT NULL,
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    PRIMARY KEY (`id`),
    KEY `user_request_logs_id_foreign` (`user_request_id`),
    CONSTRAINT `user_request_logs_id_foreign` FOREIGN KEY (`user_request_id`) REFERENCES `user_requests` (`id`)
)
    
````

[API](../api/user_requests.md)
