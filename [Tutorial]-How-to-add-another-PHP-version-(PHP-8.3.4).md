## Manual method

With Laragon, adding another PHP version is very easy. Here's how to add `PHP 8.3.4`

1. Download the latest PHP version (x64, Thread Safe): <https://windows.php.net/download/>, e.g. `php-8.3.4-Win32-vs16-x64.zip`

2. Extract the downloaded to: `{LARAGON_ROOT}\bin\php\php-8.3.4-Win32-vs16-x64`

```text
C:\laragon  
-- bin  
   ---- php  
      -------- php-8.3.4-Win32-vs16-x64  
      -------- .............  
```

3. Select the new version at: `Laragon Menu > PHP > Version > php-8.3.4-Win32-vs16-x64`
Very easy huh. That's all!

Please be noticed about PHP Version (so you can add new extensions properly)

* `x64` means 64-bit
* `x86` means 32-bit
* `nts` means Non Thread Safe

**If something's wrong, please check and install the corresponding VC Redist (VC11, VC14, VC15, [VC16](https://aka.ms/vs/16/release/VC_redist.x64.exe)...)**

Also, if you receive an error message about "nghttp2_option_set_no_rfc9113_leading_and_trailing_ws_validation", [be sure to update Apache](https://github.com/leokhoa/laragon/wiki/%5BTutorial%5D-How-to-add-another-Apache-version). It's as easy as updating PHP.

## Quick Add

Laragon can [quickly add](https://laragon.org/docs/quick-add.html) PHP versions, with only a little configuration:

### Configure

Laragon menu > Tools > Quick add > configuration...

Add the versions of PHP as required:

```ini
# PHP
php81nts=https://windows.php.net/downloads/releases/php-8.1.28-nts-Win32-vs16-x64.zip
php82nts=https://windows.php.net/downloads/releases/php-8.2.20-nts-Win32-vs16-x64.zip
php83nts=https://windows.php.net/downloads/releases/php-8.3.8-nts-Win32-vs16-x64.zip
php84nts=https://windows.php.net/downloads/releases/php-8.4.1-nts-Win32-vs17-x64.zip
```

Additional PHP versions can be seen in the current[releases](https://windows.php.net/downloads/releases/) or [archives](https://windows.php.net/downloads/releases/archives/).

Exit Laragon and re-open, to load the new config.

### Add

For example, to install PHP 8.2 NTS 64-bit:

Laragon menu > Tools > Quick add > php82nts

![image](https://github.com/leokhoa/laragon/assets/40126936/3f93caef-7032-4716-983b-1d7c7da6bdbe)

Laragon will download, unzip and copy the PHP files to %laragon_root%\bin\php\php-8.2.20-nts-Win32-vs16-x64

### Switch

To switch PHP versions:

Laragon menu > PHP > Version \[current version] > Choose the required version: e.g. php-8.2.20-nts-Win32-vs16-x64

![image](https://github.com/leokhoa/laragon/assets/40126936/8a5938da-dd34-4696-8244-4457fd878ee2)
