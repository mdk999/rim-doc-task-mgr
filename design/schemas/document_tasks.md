[Home](../../readme.md) > [Schemas](schemas.md) > DocumentTasks

### DocumentTasks table schema:

----
````mysql
create table `document_tasks`
(
    `id`          bigint unsigned NOT NULL AUTO_INCREMENT,
    `assignee_id`    bigint,
    `document_id`    bigint,
    `task_id`    bigint,
    `status`    enum('not started','started','completed'),
    `created_at`  timestamp       NULL     DEFAULT NOW(),
    `updated_at`  timestamp       NULL     DEFAULT NULL,
    `deleted_at`  timestamp       NULL     DEFAULT NULL,
    PRIMARY KEY (`id`),
    KEY `document_tasks_assignee_id_foreign` (`assignee_id`),
    KEY `document_tasks_document_id_foreign` (`document_id`),
    KEY `document_tasks_task_id_foreign` (`task_id`),
    CONSTRAINT `document_tasks_assignee_id_foreign` FOREIGN KEY (`assignee_id`) REFERENCES `users` (`id`),
    CONSTRAINT `document_tasks_document_id_foreign` FOREIGN KEY (`document_id`) REFERENCES `documents` (`id`),
    CONSTRAINT `document_tasks_task_id_foreign` FOREIGN KEY (`task_id`) REFERENCES `tasks` (`id`)
)
    
````
