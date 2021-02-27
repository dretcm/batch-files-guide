# batch-files-guide
guide about batch files.

<h1>head, message, commend, and title:</h1>

* '@echo off' only show the commands in the shell, that is to say, dont show 'C:\users\user\>' and others bases.
* 'echo' print a message.
* 'title [type you name of window]'.


```
@echo off

title test of batch files

:: this is a comend
REM this also is a comend

echo hello
pause
```

<h1>commands:</h1>

* you can use all possible commands as cmd, for example 'pause'.
* 'pause>nul' it already dont ask you.

```
@echo off

dir

start camera.exe

copy D:\games D:\my_games\super games\

ipconfig

echo and other commands

pause
pause>nul
```

* and for you files how conda, etc. use 'call'.

```
call conda activate base
call deactivate
```

* especial commands, environments varibles:

%ALLUSERSPROFILE% ------> todos los usuarios

%APPDATA% ---------> datos de programa

%PROMPT%%TEMP% y %TMP% ---------> temporales

%USERDOMAIN% -----------> obtener dominio

%USERNAME% --------------->nombre del usuario Actual

%USERPROFILE% ---------------> usuario configuracion

%programfiles% ---------------> archivos de programas

%systemroot% ----------------> windows

%homedrive% --------------> disco Raiz


para este caso nos serviria la variable de "%homedrive%". Pongamos el ejemplo con un simple batch que ejecuta el notepad
Código:
```
@echo off
title pruba
echo ahora se ejecutara el notepad
%homedrive%/windows/system32/notepad.exe
exit
```

en caso de que tubieramos en el disco c:

eso reemplaza la unidad, en conclusion son comodines que nos ayudan a la hora de programar batch.

<a href=https://www.taringa.net/+info/guia-completa-de-archivos-batch-parte-1_139ogq> Referencia o pagina de donde saco esto.</a>

<h1>variables, inputs:</h1>

* use 'set' for variables, 'set \p' for inputs, 'set \a' for operations.
* for invoquing varibale use '%',e.g: '%name%'.
* remenber that 'variable=value' always be together, no 'variable = value'.

```
@echo off

set title_program=TYPE YOU NAME
title title_program

set /p name=what is your name? 

echo hello %name%.

pause>nul
```

```
@echo off

set a=3
set b=2

set /a sum=%a% + %b%

echo the sum is: %sum%

pause>nul
```

<h1>if-if not-else:</h1>

```
@echo off

SET /p user=enter the user:

if %user%==admi (ECHO WELCOME)

pause>nul
```

```
@echo off

SET /p pet=enter animal:

IF NOT %pet%==cat (ECHO the pet isnt a cat) ELSE ECHO the pet is %pet%, good.

pause>nul
```

<h1>goto, bucle:</h1>

* Recommended call "goto" always in the begin, and create the instance always in the final, opposite case it could become a loop.

```
@echo off

goto start

:start
ECHO 1)menu
ECHO 2)shop
ECHO 3)exit
SET /p option=Enter option:
if %option%==1 (goto menu)
if %option%==2 (goto shop)
if %option%==3 (goto exit)

:menu
ECHO title - shop - help
pause
goto start

:shop
ECHO Car-31gx
ECHO WagTH
pause
goto start

:exit
exit

pause>nul
```

* infinite loop:
```
@echo off

goto example_bucle

:example_bucle
ECHO HOLA
goto example_bucle

pause>nul
```
* this isnt a loop
```
@echo off

goto example_bucle

:example_bucle
ECHO HOLA

pause>nul
```

* controlled loop:

```
@echo off

SET counter=10
goto example_bucle

:example_bucle
if %counter%==0 (goto exit) else SET /a counter= %counter% - 1
ECHO HOLA
goto example_bucle

:exit
ECHO bye
pause
exit

pause>nul
```

<h1>Message box, error</h1>

```
@echo off

::   command message box  -    message         -         system   -    title   -    temporal
echo MsgBox "Escribir un script y despues llamarlo.", 64, "NorfiPC" >%temp%\mensaje.vbs

start %temp%\mensaje.vbs
```

```
@echo off

echo coping...

COPY C:\XD D:\docs\here\ || ECHO there was mistake

pause>nul
```

