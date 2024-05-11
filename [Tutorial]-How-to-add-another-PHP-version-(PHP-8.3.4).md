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

**If something's wrong, please check and install correspond VC Redist (VC11, VC14, VC15, [VC16](https://aka.ms/vs/16/release/VC_redist.x64.exe)...)**

Also, if you receive an error message about "nghttp2_option_set_no_rfc9113_leading_and_trailing_ws_validation", [be sure to update Apache](https://github.com/leokhoa/laragon/wiki/%5BTutorial%5D-How-to-add-another-Apache-version). It's as easy as updating PHP.