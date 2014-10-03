ComposerManualInstallWinXP-
===========================

#How to install Composer on Windows XP if the .exe is not working.

**Manual Install**

1/ Check if php can be used in command line 
- Start menu -> exectute -> cmd (administrative right needed)
- try the command 
```Batchfile
php -r "echo 'test';"
```
and if you will see 
	test - at the next line 
then go to 2/
else continue
- use the command 
```Batchfile
PATH
```
and you will see something like that 
```Batchfile
PATH=C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\system32\WBEM;
```
Copy the line in a notepad and add hte windows path to your php directory like 
```Batchfile
C:\php\
``` 
and add it to the end of the line.
Like this -> 
```Batchfile
PATH=C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\system32\WBEM;C:\php\;
```
- next try 
```Batchfile
echo %APPDATA%
``` 
and you will see
```Batchfile
C:\Documents and Settings\[username]\Application Data
``` 
(windows XP)
If not
use command 
```Batchfile
set APPDATA=C:\Documents and Settings\[username]\Application Data
```
, you can change [username] with "All Users" 
and retry 
```Batchfile
echo %APPDATA%
```

2/Go to you directory
example: ```Batchfile c:\htdocs\myProject\ ```
- run command 
```Batchfile 
php -r "readfile('https://getcomposer.org/installer');" | php
```Batchfile

3/ Go to you directory
example: ```Batchfile c:\htdocs\myProject\ ```
if the project have a composer.json file
run the command : 
```Batchfile
php composer.phar install
```
You will see installation of dependencies
