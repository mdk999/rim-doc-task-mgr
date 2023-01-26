[Home](../../readme.md) > [Schemas](schemas.md) > Tasks

### Tasks table schema:

----
````mysql
create table `tasks`
(
    `id`         bigint unsigned NOT NULL AUTO_INCREMENT,
    `user_id`    bigint          NOT NULL,
    `title` varchar(255) NOT NULL,
    `status` enum('not started','started','completed'),
    `start_date` timestamp       NULL DEFAULT NULL,
    `end_date` timestamp       NULL DEFAULT NULL,
    `due_date` timestamp       NULL DEFAULT NULL,
    `created_at` timestamp       NULL DEFAULT NOW(),
    `updated_at` timestamp       NULL DEFAULT NULL,
    `deleted_at` timestamp       NULL DEFAULT NULL,
    PRIMARY KEY (`id`),
    KEY `tasks_user_id_foreign` (`user_id`),
    CONSTRAINT `tasks_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`)

)
````
[API](../api/task.md)
