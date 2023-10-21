1. cmder https://cmder.app/ scroll down to download section.
1. delete the original laragon cmder folder
1. unzip cmder.zip and create laragon.cmd file my path-> `X:\laragon\bin\cmder\config\profile.d\laragon.cmd`
1. laragon.cmd content
```
@echo off

echo %CMDER_ROOT% | findstr /i "\laragon\bin\cmder"
if "%ERRORLEVEL%" equ "0" call :laragon
exit /b 0

:laragon

:: Laragon Start -------------------------------------------------------------------


if exist "%CMDER_ROOT%\..\git" (
    set "GIT_INSTALL_ROOT=%CMDER_ROOT%\..\git"
)

if exist "%GIT_INSTALL_ROOT%\post-install.bat" (
    echo Running Git for Windows one time Post Install....
	pushd "%GIT_INSTALL_ROOT%"
    call "%GIT_INSTALL_ROOT%\git-bash.exe" --no-needs-console --hide --no-cd --command=post-install.bat
	@DEL post-install.bat

	popd
    :: cd /d %USERPROFILE%
	rem
)

for /f "delims=" %%i in ("%CMDER_ROOT%\..\..\usr") do set USER_DIR=%%~fi
set USR_DIR=%USER_DIR%

if exist "%CMDER_ROOT%\..\laragon\laragon.cmd" (
    :: call Laragon own commands
    call "%CMDER_ROOT%\..\laragon\laragon.cmd"
)


if exist "%USER_DIR%\user.cmd" (
    rem create this file and place your own command in there
    call "%USER_DIR%\user.cmd"
) else (
    echo Creating user startup file: "%USER_DIR%\user.cmd"
    (
    echo :: use this file to run your own startup commands
    echo :: use  in front of the command to prevent printing the command
    echo.
    echo :: call start-ssh-agent.cmd
    echo :: set PATH=%%USER_DIR%%\bin\whatever;%%PATH%%
	echo.
	echo :: cmd /c start http://localhost 
    echo.
    ) > "%USER_DIR%\user.cmd"
    
    :: cd /d "%CMDER_ROOT%\..\..\www"
	rem
)

:: Laragon End -------------------------------------------------------------------


exit /b 0

```
5. Add Cmder alias => edit file `X:\laragon\bin\cmder\config\user_aliases.cmd`
```
cr=composer
cri=composer install
crd=composer dump-autoload $*
cru=composer update"

pa=php artisan $*
pamm=php artisan make:model $*
pamc=php artisan make:controller $*Controller
pakg=php artisan key:generate $*
pamt=php artisan make:test $*
pamf=php artisan migrate:fresh $*
pami=php artisan migrate $*
pads=php artisan db:seed $*
pas=php artisan serve $*
tinker=php artisan tinker

ndev=npm run dev
nprod=npm run prod
nhot=npm run hot
```
6. Restart Cmder
7. pamc Post =>Controller created successfully.
8. Finish work！