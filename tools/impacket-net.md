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
