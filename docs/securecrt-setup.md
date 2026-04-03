# Setup SecureCRT

## Installation

1. Unzip and install `No_Keygen_required_SecureCRT_8.7.rar`
2. Copy the crack file to:
   ```
   C:\Program Files\VanDyke Software\Clients
   ```
3. If license error (no internet), apply manually:
   ```
   name        : shah
   company     : abcd
   serial      : 13-85-398093
   issue date  : 02-16-2021
   license key : AB9EAN QUFWPM TUSWTW 5P9E5M ABAJ8Q EZEM9Y NUAGWD 8HZ48S
   ```

## Set SecureCRT as Default Telnet Handler

1. Go to `C:\Program Files\EVE-NG`
2. Edit the registry file with SecureCRT path:

```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Classes\SecureCRT.telnet]
@="telnet"

[HKEY_CURRENT_USER\SOFTWARE\Classes\SecureCRT.telnet\DefaultIcon]
@="C:\\Program Files\\VanDyke Software\\Clients\\SecureCRT.exe,0"

[HKEY_CURRENT_USER\SOFTWARE\Classes\SecureCRT.telnet\shell\open\command]
@="\"C:\\Program Files\\VanDyke Software\\Clients\\SecureCRT.exe\" /T %1"

[HKEY_CURRENT_USER\SOFTWARE\Classes\telnet\shell\open\command]
@="\"C:\\Program Files\\VanDyke Software\\Clients\\SecureCRT.exe\" /T %1"
```

3. Run the registry edit
4. Go to **Default Apps > Choose default by link type > TELNET > change to SecureCRT**

## Single Tab (Single Instance)

Edit config file:
```
C:\Users\user\AppData\Roaming\VanDyke\Config
```

Change:
```
D:"Single Instance"=00000001
```

## Cisco Color Theme + Keyword Highlights

1. Download `Cisco_Words_-_DkBg.ini`, `Cisco_Words.ini`, `readme.txt`
2. Paste into:
   ```
   C:\Users\azrul\AppData\Roaming\VanDyke\Config\Keywords
   ```
3. In SecureCRT:
   - **Options > Edit Default Session > Appearance > Dark Pastel**
   - **Options > Edit Default Session > Keyword Highlights > Cisco Words - DkBg > Advanced > tick Bold and Color only**
