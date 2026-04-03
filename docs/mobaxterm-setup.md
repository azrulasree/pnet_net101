# MobaXterm Setup

Open `C:\Program Files\EVE-NG` and run the registry file below.

## Registry File: `win10_64bit_MobaXterm.reg`

```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Classes\MobaXterm.telnet]
@="telnet"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MobaXterm.telnet\DefaultIcon]
@="C:\\Program Files (x86)\\Mobatek\\MobaXterm\\MobaXterm.exe, 0"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MobaXterm.telnet\shell\open\command]
@="\"C:\\Program Files\\EVE-NG\\start_mobaxterm.bat\" %1"

[HKEY_CURRENT_USER\SOFTWARE\Classes\telnet\shell\open\command]
@="\"C:\\Program Files\\EVE-NG\\start_mobaxterm.bat\" %1"
```

## Batch File: `start_mobaxterm.bat`

```bat
@echo off

SET input=%1
FOR /f "tokens=1,2,3 delims=:" %%a IN ("%input%") do SET host=%%b&SET port=%%c

REM remove first 2 characters from host
SET host=%host:~2%

REM remove slash from port
SET port=%port:/=%

echo %host%
echo %port%

cd C:\Program Files (x86)\Mobatek\MobaXterm
MobaXterm.exe -newtab "telnet %host% %port%"
```
