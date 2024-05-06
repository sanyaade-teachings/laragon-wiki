# \[Tutorial\] How to manage "Quick app"

Click Menu > Quick app > Wordpress, specify a "Name" (ex. myblog), Laragon will:

- Create a corresponding database: **myblog**
- Download the latest version of **WordPress**
- Extract the code to **C:\laragon\www\myblog**
- Generate corresponding pretty URL:
  http://myblog.test

In a few minutes, you will get what you want effortlessly.

> WordPress is famous for its "5-minute quick install," but using Laragon's "**Quick app**" feature you can do it in less than 2 minutes
>
> Source: [Best WAMP Server for Local WordPress – Laragon is Easy by David McCan](https://www.webtng.com/best-wamp-server-for-local-wordpress-laragon-is-easy/)

## Some images

Quick app for a Laravel project from an online compress link (Laravel 7z):
- (missing) 0_1467989930886_quick-create-website.png

Laragon is downloading & extracting data...
- (missing) 0_1467986139777_quick-create-laravel-project.png

Laragon can handle **7z**, **tar.gz**, **zip** or **composer**. Believe or not, Laragon can create a Laravel project in **LESS THAN A MINUTE**. Just try it: **Menu > Quick app > Laravel 7z**

Laragon comes with some pre-defined projects. You can put other projects easily yourself. Just click **Menu > Quick app > Configuration** and edit the configuration file.

The file is: {LARAGON_ROOT}\usr\sites.conf
   
```text
# Options
AutoCreateDatabase=true
Cached=true

# Blank: an empty project
Blank=

# WordPress
WordPress=https://wordpress.org/latest.tar.gz

# Joomla
Joomla=https://github.com/joomla/joomla-cms/releases/download/3.8.11/Joomla_3.8.11-Stable-Full_Package.tar.gz

# Prestashop
Prestashop=https://github.com/PrestaShop/PrestaShop/releases/download/1.7.4.2/prestashop_1.7.4.2.zip

------------------------------------------------------

# Drupal
Drupal 8=https://ftp.drupal.org/files/projects/drupal-8.5.5.tar.gz
### Drupal 7=https://ftp.drupal.org/files/projects/drupal-7.59.tar.gz

------------------------------------------------------

# Laravel

Laravel=composer create-project laravel/laravel %s --prefer-dist

Laravel 7z=https://github.com/leokhoa/quick-create-laravel/releases/download/5.6.21/laravel-5.6.21.7z

### Laravel dev-develop=composer create-project laravel/laravel %s dev-develop
### Laravel 4=composer create-project laravel/laravel  %s 4.2 --prefer-dist
Lumen=composer create-project laravel/lumen  %s --prefer-dist

------------------------------------------------------

# CakePHP
CakePHP=composer create-project --prefer-dist cakephp/app %s

# Symfony
Symfony=composer create-project symfony/framework-standard-edition %s
```

## Notes:

**#**: Comment

**----**: Menu Separator

**AutoCreateDatabase**: if true, Laragon will automatically create a database corresponding to the project name.

**Cached**: if true, compressed files from remote servers will be stored in **{LARAGON_ROOT}\tmp\cached**, next time Laragon doesn't need to download them.
