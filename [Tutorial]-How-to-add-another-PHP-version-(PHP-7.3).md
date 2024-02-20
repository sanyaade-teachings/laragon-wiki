With Laragon, adding another PHP version is very easy. Here's how to add `PHP 7.3`

1. Download PHP: 
[http://windows.php.net/downloads/releases/](https://web.archive.org/web/20191120075646/http://windows.php.net/downloads/releases/)

In this case we download:

[https://windows.php.net/downloads/releases/php-7.3.0-Win32-VC15-x64.zip](https://web.archive.org/web/20191120075646/https://windows.php.net/downloads/releases/php-7.3.0-Win32-VC15-x64.zip)

2. Extract the downloaded to: `{LARAGON_ROOT}\bin\php\php-7.3.0-Win32-VC15-x64`

```text
C:\laragon  
-- bin  
   ---- php  
      -------- php-7.3.0-Win32-VC15-x64  
      -------- .............  
```

3. Select the new version at: Laragon Menu > PHP > Version > php-7.3.0-Win32-VC15-x64
Very easy huh. That's all!

Please be noticed about PHP Version (so you can add new extensions properly)

* `x64` means 64-bit
* `x86` means 32-bit
* `nts` means Non Thread Safe

**If something's wrong, please check and install correspond VC Redist (VC11, VC14, VC15...)**