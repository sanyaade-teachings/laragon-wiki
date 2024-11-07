With Laragon, adding another Apache version is very easy.

1. Download the latest Apache (64-bit): <https://www.apachelounge.com/download/>

2. Extract the downloaded files to: `{LARAGON_ROOT}\bin\apache\<version>`, e.g.

```text
C:\laragon
-- bin
    -- apache
        -- httpd-2.4.48-win64-VS16
            -- .............
```
Be sure to extract the package's files not in another version.

3. Select the new version at Laragon: `Menu > Apache > Version > httpd-2.4.48-win64-VS16`

Very easy huh. That's all forks!

## Quick Add

Laragon can [quickly add](https://laragon.org/docs/quick-add.html) Apache versions, with only a little configuration:

### Configure

Laragon menu > Tools > Quick add > configuration...

Add the versions of Apache as required:

```ini
---

# Apache
apache2462=https://www.apachelounge.com/download/VS17/binaries/httpd-2.4.62-240904-win64-VS17.zip

---
```

Additional Apache versions can be seen in the Apache lounge current [releases](https://www.apachelounge.com/download/) 
or [archives](https://www.apachelounge.com/download/additional/).

Exit Laragon and re-open, to load the new config.

### Add

For example, to install Apache 2.4.62 64-bit:

Laragon menu > Tools > Quick add > apache2462

![Screenshot 2024-11-07 181635](https://github.com/user-attachments/assets/913e9f91-3569-4d6c-a5d7-5f37402d677c)

Laragon will download, unzip and copy the Apache files to %laragon_root%\bin\apache\httpd-2.4.62-240904-win64-VS17

### Switch

To switch Apache versions:

Laragon menu > Apache > Version \[current version] > Choose the required version: e.g. httpd-2.4.62

![Screenshot 2024-11-07 181602](https://github.com/user-attachments/assets/1fd2e763-45f8-446f-9dd5-774010d6d6c2)

**Note:** Ideally, the VS17 version of Apache should match to a VS17 version of PHP. If you have problems, see the workaround for PHP 8.3 VS16 below.

## Some pics

### Folder structure

![Folder structure](https://github.com/leokhoa/laragon/assets/40126936/8e3e17b4-1a64-4a28-a844-d6314f2ea30d)

### Menu

![Laragon Menu](https://github.com/leokhoa/laragon/assets/40126936/d2a9c286-f5b4-4b6d-9e17-2b29a69d5458)

## Workaround for use of Fast CGI (non-thread safe PHP) with VS17 versions of Apache

The latest versions of PHP are compiled with VS17. If you use this with a non-thread-safe version of PHP, Laragon will correctly identify that Apache needs to use Fast-CGI and will write and include a `{LARAGON_BASE}\etc\apache2\fcgid.conf` file. 

Laragon 6 should fall back to using a compatible VS16 version of the Fast-CGI module that actually exists in `{LARAGON_BASE}\etc\apache2\modules` but unfortunately it generates a line to use a non-existent VS17 version. As a consequence when you try to start Apache you get an error about the required module not existing.

The workaround is as follows:

Try to start Apache to generate the `fcgid.conf` file. Then edit it and change the reference `mod_fcgid-2.3.9-Win64-vs17.so` to `mod_fcgid-2.3.10-win64-vs16.so`. Save the file and change the file properties to read-only. Apache should now start OK.