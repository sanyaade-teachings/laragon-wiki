Adding another MySQL version is very easy and safe with Laragon.

## MySQL

1. Download MySQL 5.7 (64-bit) or 32-bit:
   <https://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.18-winx64.zip>

2. Extract the downloaded to: {LARAGON_ROOT}\bin\mysql\mysql-5.7.18-winx64 (see below Note for MariaDB)
```text
C:\laragon
-- bin
   -- mysql
      -- mysql-5.7.18-winx64
      -- .............
```

3. Select the new version at: Laragon **Menu > MySQL > Version > mysql-5.7.18-winx64**

Very easy huh. That's all forks!

>**Hint:** You might want to set up `my.ini` for your machine configuration to speed up database performance.

## MariaDB

_**Hint:** This tutorial also applies for **MariaDB**._

<https://downloads.mariadb.org/mariadb/10.2.6/#os_group=windows>

_[Download the MariaDB 64-bit version](https://archive.mariadb.org/mariadb-10.2.6/winx64-packages/mariadb-10.2.6-winx64.zip)_

Note: If you use MariaDB, extract it to: `{LARAGON_ROOT}\bin\mysql\mariadb-10.2.6-winx64`, Laragon will automatically create a corresponding data directory for MariaDB on `{LARAGON_ROOT}\data\mariadb-{VERSION-NUMBER}`.

## Some pics

### Folder structure

![Folder structure MariaDB](https://github.com/leokhoa/laragon/assets/40126936/7be8537a-d826-4dac-a119-3ff544ca6da8)

### Menu

![Laragon MySQL Menu](https://github.com/leokhoa/laragon/assets/40126936/27edf02c-5f99-4def-a4ca-8d597c9d9036)

## MySQL 8.4 or above

MySQL >= 8.4 has removed plain \[native\] passwords and **my.ini** is a different template from MySQL 8.0. Additional steps are required to install it (see [the guide [https://gist.github.com/meorajrul/b57803bf1b4ddfd2f93e6ad37c3ac5f2]](https://gist.github.com/meorajrul/b57803bf1b4ddfd2f93e6ad37c3ac5f2) by [@MeorA](https://github.com/meorajrul) for full details). But in essence, before attempting to run the new version of MySQL you need to do a few simple steps:

1. In Laragon, select the new version of MySQL *but do **not** start it yet* (because you need to find out the random password and change it).
2. Edit the `my.ini` file in the new MySQL or MariaDB product version directory and remove the line `default_authentication_plugin=mysql_native_password`. Save the file and make the `my.ini` file read-only from file properties.
3. Open a command prompt in `{LARAGON_ROOT}\data` and if necessary create a new `mysql-{VERSION-NUMBER}` sub-directory, and CD to that sub-directory.
4. Run `mysqld --initialize --datadir="{LARAGON_ROOT}\data\mysql-{VERSION}" --basedir="{LARAGON_ROOT}\bin\mysql\mysql-{VERSION}" --console` replacing the directory names as necessary. When you get an output line which says `A temporary password is generated for root@localhost:` then make a note of / select and copy the random password that was generated.
5. From Laragon, open Heidi (session manager), type or paste the password into the password box and click `Save`.
6. In Laragon, Start MySQL/MariaDB and check that it starts OK.
7. In Heidi, connect to the database (you may need to restart Heidi). It should prompt you to change the root password. Once you have done this...
8. In Laragon, Stop and Start MySQL/MariaDB again to make sure that the password change has worked, and check that Heidi can also connect.

