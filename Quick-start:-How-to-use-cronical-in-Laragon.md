Usually, CMS and other software need to run tasks periodically. This can be realizied by running a website script (e.h. with a specific path) or running a console command - on Webhosting plattforms often incentived with a better performance, less overhead and longer script runtime.

Luckily, Laragon comes with Cronical to run those tasks as you would on an own server.

## Setting up Cronical

Also, have a look at these resources first as 

1. First, run `C:\laragon\bin\cronical\Cronical.exe --install` from your command line.
2. To start the service manually, run `net start cronical` afterwards.

If succeded, you'll find the first log next to `cronical.exe` in `C:\laragon\\bin\cronical\` (or wherever your installation of Laragon is)

Also, have a look at these resources first, as long as this Wiki page is just about to be created.
* https://pen-y-fan.github.io/2023/01/28/how-to-run-cron-jobs-on-windows/ by @pen-y-fan
* 


## Configuring Cronical

Croincal came with a default configuration file `cronical.dat` that contains this information:

```
# === Format ===
#
# *    *    *    *    *  command to execute
# ¦    ¦    ¦    ¦    ¦
# ¦    ¦    ¦    ¦    +----- day of week (0 - 6) (0 to 6 are Sunday to Saturday, or use names)
# ¦    ¦    ¦    +---------- month (1 - 12)
# ¦    ¦    +--------------- day of month (1 - 31)
# ¦    +-------------------- hour (0 - 23)
# +------------------------- min (0 - 59)
#
# === Examples ===
#
# *    *    * * *        cmd /c echo Every minute
# */5  *    * * *        cmd /c echo Every five minutes
# 0    8,17 * * *        cmd /c echo At 08:00, 12:00 and 17:00
# 0,30 *    * * *        cmd /c echo Every hour at :00, :15, :30 and :45
# 0    2    1 * *        cmd /c echo At 02:00 the 1st of every month
# 0    2    1 1 *        cmd /c echo At 02:00 the 1st of January
# 30   2    * * sat,sun  cmd /c echo At 02:30 every Saturday or Sunday
#
# @reboot                cmd /c echo Run when the service is started (typically on reboot)
# @yearly                cmd /c echo Once a year, typically midnight Jan 1st
# @annually              cmd /c echo Same as @yearly
# @monthly               cmd /c echo Midnight on the first of every month
# @weekly                cmd /c echo Midnight on every Sunday
# @daily                 cmd /c echo Midnight every day
# @hourly                cmd /c echo Every hour
#
# @service               cmd /k echo Start and keep running, restarting if it exits


# === Global settings ===

RunMissedJobs = true            # On startup, run any missed jobs
ServiceChecks = 15              # Check services every 15 seconds, default is every second
Timeout       = 3600            # Jobs may run for up to 1 hour


# === Settings for each job ===

# Home          = 
# MailFrom      = cronical@example.com
# MailTo        = admin@example.com
# MailStdOut    = false
# MailCc      = 
# MailBcc     = 
# SmtpHost      = mail.example.com
# SmtpSSL       = false
# SmtpUser    = 
# SmtpPass    = 


# === Jobs to run ===

# In order to run apps as a different user - for instance, for backing up registry - either register
# the service under a different user name in Services, or use the psexec utility to impersonate
# another user. See http://technet.microsoft.com/en-us/sysinternals/bb897553.aspx

# @reboot cmd /c echo Hello, world! I am Cronical. && timeout /t 120


# --- Jobs --------------------------------------------------------------------------
```

To create a job, simply follow the instructions here. Add your jobs under the "Jobs"-section of this configuration file.


### Example Cron for WordPress

<https://developer.wordpress.org/plugins/cron/>

``` 
* * * * * php -f C:\laragon\www\site\wp-cron.php
```
### Example Cron for REDAXO CMS

```
* * * * * php -f C:\laragon\www\my-project\bin\console cronjob:run
```

## Further information

<https://github.com/mgefvert/Cronical>