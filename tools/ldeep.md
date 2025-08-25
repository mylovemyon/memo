### auth_policis
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice auth_policies

```


### bitlockerkeys
```
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice bitlockerkeys

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
 "(objectClass=*)"なので割愛
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


### pkis
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice pkis
Certificate Authorities
```


### pso
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice pso

```


### sccm
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice sccm
[!] invalid attribute type mSSMSDefaultMP. Can't find SCCM management points
```


### schema
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice schema
CN=Schemaで大量なので割愛
```


### server_info
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice server_info              
altServer []
configurationNamingContext ['CN=Configuration,DC=htb,DC=local']
currentTime ['20250825104227.0Z']
defaultNamingContext ['DC=htb,DC=local']
dnsHostName ['FOREST.htb.local']
domainControllerFunctionality ['7']
domainFunctionality ['7']
dsServiceName ['CN=NTDS Settings,CN=FOREST,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=htb,DC=local']
forestFunctionality ['7']
highestCommittedUSN ['3263212']
isGlobalCatalogReady ['TRUE']
isSynchronized ['TRUE']
ldapServiceName ['htb.local:forest$@HTB.LOCAL']
namingContexts ['DC=htb,DC=local', 'CN=Configuration,DC=htb,DC=local', 'CN=Schema,CN=Configuration,DC=htb,DC=local', 'DC=DomainDnsZones,DC=htb,DC=local', 'DC=ForestDnsZones,DC=htb,DC=local']
rootDomainNamingContext ['DC=htb,DC=local']
schemaNamingContext ['CN=Schema,CN=Configuration,DC=htb,DC=local']
serverName ['CN=FOREST,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=htb,DC=local']
subschemaSubentry ['CN=Aggregate,CN=Schema,CN=Configuration,DC=htb,DC=local']
supportedCapabilities ['1.2.840.113556.1.4.800', '1.2.840.113556.1.4.1670', '1.2.840.113556.1.4.1791', '1.2.840.113556.1.4.1935', '1.2.840.113556.1.4.2080', '1.2.840.113556.1.4.2237']
supportedControl ['1.2.840.113556.1.4.319', '1.2.840.113556.1.4.801', '1.2.840.113556.1.4.473', '1.2.840.113556.1.4.528', '1.2.840.113556.1.4.417', '1.2.840.113556.1.4.619', '1.2.840.113556.1.4.841', '1.2.840.113556.1.4.529', '1.2.840.113556.1.4.805', '1.2.840.113556.1.4.521', '1.2.840.113556.1.4.970', '1.2.840.113556.1.4.1338', '1.2.840.113556.1.4.474', '1.2.840.113556.1.4.1339', '1.2.840.113556.1.4.1340', '1.2.840.113556.1.4.1413', '2.16.840.1.113730.3.4.9', '2.16.840.1.113730.3.4.10', '1.2.840.113556.1.4.1504', '1.2.840.113556.1.4.1852', '1.2.840.113556.1.4.802', '1.2.840.113556.1.4.1907', '1.2.840.113556.1.4.1948', '1.2.840.113556.1.4.1974', '1.2.840.113556.1.4.1341', '1.2.840.113556.1.4.2026', '1.2.840.113556.1.4.2064', '1.2.840.113556.1.4.2065', '1.2.840.113556.1.4.2066', '1.2.840.113556.1.4.2090', '1.2.840.113556.1.4.2205', '1.2.840.113556.1.4.2204', '1.2.840.113556.1.4.2206', '1.2.840.113556.1.4.2211', '1.2.840.113556.1.4.2239', '1.2.840.113556.1.4.2255', '1.2.840.113556.1.4.2256', '1.2.840.113556.1.4.2309']
supportedExtension ['1.3.6.1.4.1.1466.20037', '1.3.6.1.4.1.1466.101.119.1', '1.2.840.113556.1.4.1781', '1.3.6.1.4.1.4203.1.11.3', '1.2.840.113556.1.4.2212']
supportedFeatures []
supportedLDAPPolicies ['MaxPoolThreads', 'MaxPercentDirSyncRequests', 'MaxDatagramRecv', 'MaxReceiveBuffer', 'InitRecvTimeout', 'MaxConnections', 'MaxConnIdleTime', 'MaxPageSize', 'MaxBatchReturnMessages', 'MaxQueryDuration', 'MaxDirSyncDuration', 'MaxTempTableSize', 'MaxResultSetSize', 'MinResultSets', 'MaxResultSetsPerConn', 'MaxNotificationPerConn', 'MaxValRange', 'MaxValRangeTransitive', 'ThreadMemoryLimit', 'SystemMemoryLimitPercent']
supportedLDAPVersion ['3', '2']
supportedSASLMechanisms ['GSSAPI', 'GSS-SPNEGO', 'EXTERNAL', 'DIGEST-MD5']
vendorName []
vendorVersion []
```


### shadow_principals
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice shadow_principals

```


### silos
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice silos

```


### smsa
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice smsa

```


### subnets
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice subnets   

```


### templates
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice templates   

```


### trusts
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice trusts

```


### users
#### users all
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users all   
santi
mark
andy
svc-alfresco
lucinda
sebastien
HealthMailbox0659cc1
HealthMailbox7108a4e
HealthMailboxb01ac64
HealthMailboxfd87238
HealthMailbox83d6781
HealthMailbox6ded678
HealthMailbox968e74d
HealthMailbox670628e
HealthMailboxc0a90c9
HealthMailboxfc9daad
HealthMailboxc3d7722
SM_1ffab36a2f5f479cb
SM_c75ee099d0a64c91b
SM_7c96b981967141ebb
SM_9b69f1b9d2cc45549
SM_1b41c9286325456bb
SM_681f53d4942840e18
SM_75a538d3025e4db9a
SM_ca8c2ed5bdab4dc9b
SM_2c8eef0a09b545acb
$331000-VK4ADACQNUCA
krbtgt
DefaultAccount
Guest
Administrator
```
#### users spn
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users spn

```
#### users enabled
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users enabled
santi
mark
andy
svc-alfresco
lucinda
sebastien
HealthMailbox0659cc1
HealthMailbox7108a4e
HealthMailboxb01ac64
HealthMailboxfd87238
HealthMailbox83d6781
HealthMailbox6ded678
HealthMailbox968e74d
HealthMailbox670628e
HealthMailboxc0a90c9
HealthMailboxfc9daad
HealthMailboxc3d7722
Administrator
```
#### users disabled
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users disabled
SM_1ffab36a2f5f479cb
SM_c75ee099d0a64c91b
SM_7c96b981967141ebb
SM_9b69f1b9d2cc45549
SM_1b41c9286325456bb
SM_681f53d4942840e18
SM_75a538d3025e4db9a
SM_ca8c2ed5bdab4dc9b
SM_2c8eef0a09b545acb
$331000-VK4ADACQNUCA
krbtgt
DefaultAccount
Guest
```
#### users locked
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users locked  

```
#### users nopasswordexpire
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users nopasswordexpire
santi
mark
andy
svc-alfresco
lucinda
sebastien
HealthMailbox0659cc1
HealthMailbox7108a4e
HealthMailboxb01ac64
HealthMailboxfd87238
HealthMailbox83d6781
HealthMailbox6ded678
HealthMailbox968e74d
HealthMailbox670628e
HealthMailboxc0a90c9
HealthMailboxfc9daad
HealthMailboxc3d7722
DefaultAccount
Guest
```
#### users passwordexpired
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users passwordexpired

```
#### users passwordnotrequired
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users passwordnotrequired
$331000-VK4ADACQNUCA
DefaultAccount
Guest
```
#### users nokrbpreauth
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users nokrbpreauth       
svc-alfresco
```
#### users reversible 
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice users reversible  

```


### zones
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice zones   
[+] Domain zones:
htb.local

[+] Forest zones:
_msdcs.htb.local
```


### from_guid
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice from_guid a8133c53-217c-40e2-81cb-887e0f61bdb0
Administrator
```


### from_sid
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice from_sid S-1-5-21-3072663084-364016917-1341370565-500
Administrator
```


### laps
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice laps   
invalid attribute type msLAPS-EncryptedPassword
[!] No LAPS related attribute has been detected
```


### memberships
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice memberships administrator
CN=Organization Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=Group Policy Creator Owners,CN=Users,DC=htb,DC=local
CN=Domain Admins,CN=Users,DC=htb,DC=local
CN=Enterprise Admins,CN=Users,DC=htb,DC=local
CN=Schema Admins,CN=Users,DC=htb,DC=local
CN=Administrators,CN=Builtin,DC=htb,DC=local
CN=Domain Users,CN=Users,DC=htb,DC=local
```


### membersof
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice membersof administrators
[GROUP] CN=Domain Admins,CN=Users,DC=htb,DC=local
[GROUP] CN=Enterprise Admins,CN=Users,DC=htb,DC=local
[USER] CN=Administrator,CN=Users,DC=htb,DC=local
```


### object
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice object administrator
Administrators (group)
Administrator
```


### sddl
ユーザのntSecurityDescriptorを調査
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice sddl administrator     
[{
  "dn": "CN=Administrator,CN=Users,DC=htb,DC=local",
  "nTSecurityDescriptor": {
    "DACL": {
      "ACEs": [
        {
          "Access Required": {
            "Access SACL": false,
            "Ads Control Access": false,
            "Ads Create Child": true,
            "Ads Delete Child": true,
            "Ads Delete Tree": false,
            "Ads List": true,
            "Ads List Object": false,
            "Ads Read Prop": false,
            "Ads Self Write": false,
            "Ads Write Prop": false,
            "Delete": false,
            "Generic All": false,
            "Generic Execute": false,
            "Generic Read": false,
            "Generic Write": false,
            "Maximum Allowed": false,
            "Read Control": false,
            "Synchronise": false,
            "Write DAC": false,
            "Write Owner": false
          },
          "GUID": "{c975c901-6cea-4b6f-8319-d67f45449506}",
          "Inherited GUID": "{4828cc14-1437-45bc-9b07-ad6f015e5f28}",
          "Object Flags": {
            "Inherited Object Type Present": true,
            "Object Type Present": true
          },
          "Raw Access Required": 7,
          "Raw Flags": 10,
          "Raw Object Flags": 3,
          "Raw Type": 5,
          "SID": "S-1-5-21-3072663084-364016917-1341370565-1118",
          "Size": 72,
          "Type": "Access Allowed Object"
        },
        {
          "Access Required": {
            "Access SACL": false,
・・・
```


### silo
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice silo all
[!] Silo all does not exists
[]
```


### zones
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice zone htb.local
[+] Domain records:
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
```


### enum_users
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice enum_users /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt
mark
andy
administrator
sebastien
santi
lucinda
```


### search
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice search '(sAMAccountName=administrator)' objectGUID
[{
  "dn": "CN=Administrator,CN=Users,DC=htb,DC=local",
  "objectGUID": "{a8133c53-217c-40e2-81cb-887e0f61bdb0}"
}]
```


### whoami
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice whoami
HTB\svc-alfresco
```


### add_to_group
```sh
└─$ ldeep ldap -d htb.local -s 10.129.143.161 -t ntlm -u svc-alfresco -p s3rvice add_to_group 'CN=svc-alfresco,DC=htb,DC=local' 'CN=administrators,CN=Builtin,DC=htb,DC=local'
[!] Unable to add CN=svc-alfresco,DC=htb,DC=local to CN=administrators,CN=Builtin,DC=htb,DC=local, check privileges or dn

```
