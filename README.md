# batch-files-guide
guide about batch files.

<h1>head, message and title:</h1>

* '@echo off' only show the commands in the shell, that is to say, dont show 'C:\users\user\>' and others bases.
* 'echo' print a message.
* 'title [type you name of window]'.


```
@echo off
title test of batch files
echo hello
pause
```

<h1>commands</h1>

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

<h1>variables, inputs</h1>

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
