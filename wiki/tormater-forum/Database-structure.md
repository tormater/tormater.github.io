---
title: Database structure
---

## Category structure

| Field               | Value                                | Description                         |
|---------------------|--------------------------------------|-------------------------------------|
| categoryid          | int unsigned NOT NULL AUTO_INCREMENT | Unique identifier for category.     |
| categoryname        | varchar(255) NOT NULL                | Display name for category.          |
| categorydescription | varchar(255) NOT NULL                | Description for category.           |
| order               | int unsigned NOT NULL DEFAULT '0'    | Controls position in category list. |

## Post structure

| Field     | Value                                | Description                         |
|-----------|--------------------------------------|-------------------------------------|
| postid    | int unsigned NOT NULL AUTO_INCREMENT | Unique identifier for post.         |
| thread    | int unsigned NOT NULL                | Parent thread for post.             |
| user      | int unsigned NOT NULL                | User who created the post.          |
| timestamp | int unsigned NOT NULL                | Post creation time.                 |
| editedby  | int unsigned DEFAULT NULL            | User responsible for last edit.     |
| edittime  | int unsigned DEFAULT NULL            | Last edit time.                     |
| deletedby | int unsigned DEFAULT NULL            | User responsible for post deletion. |
| content   | text NOT NULL                        | The post's content.                 |

## Thread structure

| Field        | Value                                | Description                    |
|--------------|--------------------------------------|--------------------------------|
| threadid     | int unsigned NOT NULL AUTO_INCREMENT | Unique identifier for thread.  |
| title        | varchar(255) NOT NULL                | Display name for thread.       |
| sticky       | tinyint(1) NOT NULL DEFAULT '0'      | Is thread stickied?            |
| locked       | tinyint(1) NOT NULL DEFAULT '0'      | Is thread locked?              |
| pinned       | tinyint(1) NOT NULL DEFAULT '0'      | Is thread pinned?              |
| posts        | int unsigned NOT NULL                | Number of posts in thread.     |
| startuser    | int unsigned NOT NULL                | User who started the thread.   |
| starttime    | int unsigned NOT NULL                | Thread creation date.          |
| lastpostuser | int unsigned NOT NULL                | User who made the latest post. |
| lastposttime | int unsigned NOT NULL                | Time of latest post.           |
| category     | int unsigned NOT NULL                | Parent category of thread.     |
| draft        | tinyint(1) NOT NULL DEFAULT '0'      | Is thread a draft?             |

## User structure

| Field            | Value                                                                            | Description                   |
|------------------|----------------------------------------------------------------------------------|-------------------------------|
| userid           | int unsigned NOT NULL AUTO_INCREMENT                                             | Unique identifier for user.   |
| username         | varchar(26) NOT NULL                                                             | Display name for user.        |
| email            | varchar(255) NOT NULL                                                            | User's email address.         |
| password         | varchar(128) NOT NULL                                                            | User's password hash.         |
| role             | enum('Administrator','Moderator','Member','Suspended') NOT NULL DEFAULT 'Member' | User's role.                  |
| jointime         | int unsigned NOT NULL                                                            | User creation date.           |
| lastactive       | int unsigned DEFAULT NULL                                                        | Last page visit time.         |
| lastaction       | varchar(255) DEFAULT NULL                                                        | User's last action.           |
| color            | tinyint unsigned NOT NULL DEFAULT '1'                                            | User's post color.            |
| ip               | varchar(128) NOT NULL                                                            | User's IP Address.            |
| salt             | char(64) NOT NULL                                                                | User's password salt.         |
| verified         | tinyint(1) NOT NULL DEFAULT '0'                                                  | Has the user been verified?   |
| deleted          | tinyint(1) NOT NULL DEFAULT '0'                                                  | Has the user been deleted?    |
| signature        | varchar(512) DEFAULT NULL                                                        | The user's post signature.    |
| bio              | varchar(2048) DEFAULT NULL                                                       | The user's profile biography. |
| avatar           | enum('none', 'png', 'jpg', 'gif', 'webp') NOT NULL DEFAULT 'none'                        | The user's avatar format.     |
| avataruploadtime | int unsigned DEFAULT NULL                                                        | Time of avatar upload.        |

## Login structure

| Field | Value                 | Description       |
|-------|-----------------------|-------------------|
| ip    | varchar(128) NOT NULL | Login IP Address. |
| time  | int unsigned NOT NULL | Time of login.    |

## Draft structure

| Field     | Value                 | Description                 |
|-----------|-----------------------|-----------------------------|
| user      | int unsigned NOT NULL | User who created the draft. |
| thread    | int unsigned NOT NULL | Parent thread of draft.     |
| timestamp | int unsigned NOT NULL | Date of draft creation.     |
| content   | text NOT NULL         | Draft content.              |

## Audit log structure

| Field    | Value                                                                                                                                                                                   | Description                       |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| time     | int unsigned DEFAULT NULL                                                                                                                                                               | Date of log entry.                |
| actionid | int unsigned NOT NULL AUTO_INCREMENT                                                                                                                                                    | Unique identifier for log entry.  |
| action   | enum('edit_post','delete_post','hide_post','rename_thread','delete_thread', 'move_thread','edit_labels','delete_avatar','edit_role','delete_user', 'change_forum_setting') DEFAULT NULL | Type of action.                   |
| userid   | int unsigned NOT NULL                                                                                                                                                                   | ID of responsible user.           |
| victimid | int unsigned NOT NULL                                                                                                                                                                   | ID of victim.                     |
| before   | text DEFAULT NULL                                                                                                                                                                       | Content before action.            |
| after    | text DEFAULT NULL                                                                                                                                                                       | Content after action.             |
| context  | text DEFAULT NULL                                                                                                                                                                       | More information about log entry. |
