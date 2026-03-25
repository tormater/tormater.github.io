---
title: Installing your forum
---
### Prerequisites 
Before you install your forum, you will need to have PHP 7.4 (and up) with either `Apache 2` or `nginx` installed, as well as `MySQL`/`MariaDB`.
<br>Your PHP install must have the following extensions for Tormater Forum to work properly: `php-mysqli`, `php-gd`, `php-mbstring`.
<br>You may also want to enable `.htaccess` overriding if you're using Apache, however, this is optional.

Once you have all of those installed, you must create a MySQL user and a database for the forum. Keep track of your MySQL user credentials--you will need them later.

### Installation
Upload Tormater Forum to your server, and connect to your forum's index (eg, www.example.com/forum/index.php). Depending on your hosting provider, you may need to change file permissions after upload. If required, navigate to the forum, and `chmod 777` every file/directory.

From here, fill out the installer with your MySQL details. Make sure that your MySQL user has permission to read and write your database.

![image](https://github.com/user-attachments/assets/aeac3bb4-fd9f-4132-9e66-7e418ba87df0)

Afterwards, pick out a username, email, and password for your administrator account and click the Install Tormater Forum button to install your forum.
