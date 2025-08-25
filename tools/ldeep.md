### auth_policis
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice auth_policies -v
[]
```


### bitlockerkeys
```
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice bitlockerkeys -v
[]
 ```


### computers
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice computers    
EXCH01.htb.local
FOREST.htb.local
```


### conf
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice conf
 "(objectClass=*)"なので全出力
```


### delegations
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice delegations all
FOREST$:unconstrained:
```


### dns_records
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice dns_records  
[+] Domain records:
M.ROOT-SERVERS.NET AAAA 2001:dc3::35
L.ROOT-SERVERS.NET AAAA 2001:500:9f::42
K.ROOT-SERVERS.NET AAAA 2001:7fd::1
J.ROOT-SERVERS.NET AAAA 2001:503:c27::2:30
I.ROOT-SERVERS.NET AAAA 2001:7fe::53
H.ROOT-SERVERS.NET AAAA 2001:500:1::53
G.ROOT-SERVERS.NET A 192.112.36.4
F.ROOT-SERVERS.NET AAAA 2001:500:2f::f
E.ROOT-SERVERS.NET A 192.203.230.10
D.ROOT-SERVERS.NET AAAA 2001:500:2d::d
C.ROOT-SERVERS.NET AAAA 2001:500:2::c
B.ROOT-SERVERS.NET AAAA 2001:500:84::b
A.ROOT-SERVERS.NET AAAA 2001:503:ba3e::2:30
@ NS M.ROOT-SERVERS.NET
@ NS L.ROOT-SERVERS.NET
@ NS K.ROOT-SERVERS.NET
@ NS J.ROOT-SERVERS.NET
@ NS I.ROOT-SERVERS.NET
@ NS H.ROOT-SERVERS.NET
@ NS G.ROOT-SERVERS.NET
@ NS F.ROOT-SERVERS.NET
@ NS E.ROOT-SERVERS.NET
@ NS D.ROOT-SERVERS.NET
@ NS C.ROOT-SERVERS.NET
@ NS B.ROOT-SERVERS.NET
@ NS A.ROOT-SERVERS.NET
EXCH01 AAAA dead:beef::9548:657:1098:7fdd
EXCH01 A 10.10.10.7
forest AAAA dead:beef::e826:a024:b25:d8a7
forest AAAA dead:beef::8a
forest A 10.129.143.161
_msdcs NS forest.htb.local
@ AAAA dead:beef::8a
@ AAAA dead:beef::e826:a024:b25:d8a7
@ NS forest.htb.local
@ A 10.129.143.161

[+] Forest records:
@ NS forest.htb.local

[+] Legacy records:
M.ROOT-SERVERS.NET AAAA 2001:dc3::35
L.ROOT-SERVERS.NET AAAA 2001:500:9f::42
K.ROOT-SERVERS.NET AAAA 2001:7fd::1
J.ROOT-SERVERS.NET AAAA 2001:503:c27::2:30
I.ROOT-SERVERS.NET AAAA 2001:7fe::53
H.ROOT-SERVERS.NET AAAA 2001:500:1::53
G.ROOT-SERVERS.NET A 192.112.36.4
F.ROOT-SERVERS.NET AAAA 2001:500:2f::f
E.ROOT-SERVERS.NET A 192.203.230.10
D.ROOT-SERVERS.NET AAAA 2001:500:2d::d
C.ROOT-SERVERS.NET AAAA 2001:500:2::c
B.ROOT-SERVERS.NET AAAA 2001:500:84::b
A.ROOT-SERVERS.NET AAAA 2001:503:ba3e::2:30
@ NS M.ROOT-SERVERS.NET
@ NS L.ROOT-SERVERS.NET
@ NS K.ROOT-SERVERS.NET
@ NS J.ROOT-SERVERS.NET
@ NS I.ROOT-SERVERS.NET
@ NS H.ROOT-SERVERS.NET
@ NS G.ROOT-SERVERS.NET
@ NS F.ROOT-SERVERS.NET
@ NS E.ROOT-SERVERS.NET
@ NS D.ROOT-SERVERS.NET
@ NS C.ROOT-SERVERS.NET
@ NS B.ROOT-SERVERS.NET
@ NS A.ROOT-SERVERS.NET
```


### domain_policy
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice domain_policy
distinguishedName: DC=htb,DC=local
lockoutDuration: 30 mins
lockOutObservationWindow: 30.0 mins
lockoutThreshold: 0
maxPwdAge: 10675199 days
minPwdAge: 1 days
minPwdLength: 7
pwdProperties: 
pwdHistoryLength: 24
ms-DS-MachineAccountQuota: 10
msDS-Behavior-Version: Windows Server 2016
dc: htb
dn: DC=htb,DC=local
```


### fsmo
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice fsmo         
Domain naming master     FOREST.htb.local
Schema master            FOREST.htb.local
RID pool manager         FOREST.htb.local
Infrastructure master    FOREST.htb.local
PDC                      FOREST.htb.local
```


### gmsa
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice gmsa

```


### gpo
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice gpo 
{6AC1786C-016F-11D2-945F-00C04fB984F9}: Default Domain Controllers Policy
{31B2F340-016D-11D2-945F-00C04FB984F9}: Default Domain Policy
```


### groups
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice groups 
test
Privileged IT Accounts
Service Accounts
$D31000-NSEL5BRJ63V7
ExchangeLegacyInterop
Exchange Windows Permissions
Managed Availability Servers
Exchange Trusted Subsystem
Exchange Servers
Security Administrator
Security Reader
Compliance Management
Hygiene Management
Delegated Setup
Server Management
Discovery Management
Records Management
Help Desk
UM Management
Public Folder Management
View-Only Organization Management
Recipient Management
Organization Management
DnsUpdateProxy
DnsAdmins
Enterprise Key Admins
Key Admins
Protected Users
Cloneable Domain Controllers
Enterprise Read-only Domain Controllers
Read-only Domain Controllers
Denied RODC Password Replication Group
Allowed RODC Password Replication Group
Terminal Server License Servers
Windows Authorization Access Group
Incoming Forest Trust Builders
Pre-Windows 2000 Compatible Access
Account Operators
Server Operators
RAS and IAS Servers
Group Policy Creator Owners
Domain Guests
Domain Users
Domain Admins
Cert Publishers
Enterprise Admins
Schema Admins
Domain Controllers
Domain Computers
Storage Replica Administrators
System Managed Accounts Group
Remote Management Users
Access Control Assistance Operators
Hyper-V Administrators
RDS Management Servers
RDS Endpoint Servers
RDS Remote Access Servers
Certificate Service DCOM Access
Event Log Readers
Cryptographic Operators
IIS_IUSRS
Distributed COM Users
Performance Log Users
Performance Monitor Users
Network Configuration Operators
Remote Desktop Users
Replicator
Backup Operators
Print Operators
Guests
Users
Administrators
```


### machines
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice machines
EXCH01$
FOREST$
```


### ou
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice ou   
DC=htb,DC=local
  [gPLink]:
    * Default Domain Policy
OU=Employees,DC=htb,DC=local
OU=Security Groups,DC=htb,DC=local
OU=Service Accounts,DC=htb,DC=local
OU=Sysadmins,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Helpdesk,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=IT Management,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Reception,OU=Employees,DC=htb,DC=local
OU=Marketing,OU=Employees,DC=htb,DC=local
OU=Sales,OU=Employees,DC=htb,DC=local
OU=Application Support,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Developers,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Exchange Administrators,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Microsoft Exchange Security Groups,DC=htb,DC=local
OU=Domain Controllers,DC=htb,DC=local
  [gPLink]:
    * Default Domain Controllers Policy
```
