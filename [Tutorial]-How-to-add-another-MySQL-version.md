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

## MariaDB

_**Hint:** This tutorial also applies for **MariaDB**._

<https://downloads.mariadb.org/mariadb/10.2.6/#os_group=windows>

_[Download the MariaDB 64-bit version](https://archive.mariadb.org/mariadb-10.2.6/winx64-packages/mariadb-10.2.6-winx64.zip)_

Note: If you use MariaDB, extract it to: **{LARAGON_ROOT}\bin\mysql\mariadb-10.2.6-winx64**, Laragon will automatically create correspond DataDir for MariaDB on **data/mariadb**

## Some pics

### Folder structure

![Folder structure MariaDB](https://github.com/leokhoa/laragon/assets/40126936/7be8537a-d826-4dac-a119-3ff544ca6da8)

### Menu

![Laragon MySQL Menu](https://github.com/leokhoa/laragon/assets/40126936/27edf02c-5f99-4def-a4ca-8d597c9d9036)

## MySQL 8.4

MySQL 8.4 has removed plain \[native\] passwords and **my.ini** is a different template from MySQL 8.0. Additional steps are required to install it, see the guide by [MeorA](https://github.com/meorajrul)
 <https://gist.github.com/meorajrul/b57803bf1b4ddfd2f93e6ad37c3ac5f2>