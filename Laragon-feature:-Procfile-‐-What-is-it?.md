**recovered from**: `http://forum.laragon.org/topic/476`

You can read about Procfile here at Heroku: [https://devcenter.heroku.com/articles/procfile](https://devcenter.heroku.com/articles/procfile)

However, Laragon makes Procfile more convenient to use with GUI. On Laragon all processes on Procfile will be displayed on Menu > Laragon
Some other differences on Laragon are:

1. A process name can have spaces. For example: **My Cool App**
2. You can add autorun to make the process auto triggered when Laragon starts
3. You can hide (don't show Console) a process if you quote its command. For example: "php artisan serve"
4. You can set PWD=xxx - xxx is Path of current process
5. You can have env_file=yyy - yyy is Path to your Environment File.
Here is format of a Procfile:
```shell
# Format:
; Program Name: autorun COMMANDS env_file=PATH_OF_FILE pwd=PATH_OF_WORKING_DIR ENV_VAR1=VALUE ENV_VAR2="VALUE WITH SPACE"

# Help:
; Program Name: Will be displayed on Procfile or Tools' Menu (can contains space)
; autorun: Your COMMANDS will be run automatically when Laragon starts
; COMMANDS: A command or a series of commands (separated by & )
; env_file: You can set environment variables directly or put them to the file
; PWD: Current working directory - where the COMMANDS run

# Examples:
; My Cool App: autorun node start $PORT PORT=9000 env_file=usr\my_file.env  PWD=usr/proj/myapp DB_HOST=1.2.3.4 DB_PORT=9999 DB_USER=user DB_PASS="!$Ab.cs3cre1" DB_NAME=cooldb
; Awesome Tool: "PATH HAS SPACES SHOULD BE QUOTED LIKE THIS"

------------------------------------------------------------------------------
```

> [!NOTE]
> * pwd is case-insensitive.
> * autorun is case-insensitive.
> * Your env_file may look like this:
> ```shell
> VAR1="VALUE WITH SPACE"
> DB_HOST=1.2.3.4
> DB_PORT=9999
> DB_USER=user
> DB_PASS=!$Ab.cs3cre1
> ```