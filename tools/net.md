## rpc
### info
```sh
└─$ net rpc info -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Domain Name: HTB
Domain SID: S-1-5-21-3072663084-364016917-1341370565
Sequence number: 1
Num users: 105
Num domain groups: 0
Num local groups: 0
```

### user
```sh
└─$ net rpc user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
$331000-VK4ADACQNUCA
Administrator
andy
DefaultAccount
Guest
HealthMailbox0659cc1
HealthMailbox670628e
HealthMailbox6ded678
HealthMailbox7108a4e
HealthMailbox83d6781
HealthMailbox968e74d
HealthMailboxb01ac64
HealthMailboxc0a90c9
HealthMailboxc3d7722
HealthMailboxfc9daad
HealthMailboxfd87238
krbtgt
lucinda
mark
santi
sebastien
SM_1b41c9286325456bb
SM_1ffab36a2f5f479cb
SM_2c8eef0a09b545acb
SM_681f53d4942840e18
SM_75a538d3025e4db9a
SM_7c96b981967141ebb
SM_9b69f1b9d2cc45549
SM_c75ee099d0a64c91b
SM_ca8c2ed5bdab4dc9b
svc-alfresco
```
#### user info
```sh
└─$ net rpc user info administrator -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Enterprise Admins
Organization Management
Domain Users
Group Policy Creator Owners
Domain Admins
Schema Admins
```
#### user add
```sh
└─$ net rpc user add user user123$ -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Added user 'user'.
```
#### user password
```sh
└─$ net rpc user password user user123% -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### user rename
```sh
└─$ net rpc user rename user user1  -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Renamed user from user to user1
```
#### user delete
```sh
└─$ net rpc user delete user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Deleted user 'user'.
```

### group
#### group list
##### rpc group list global
```sh
└─$ net rpc group list global -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210 
$D31000-NSEL5BRJ63V7
Cloneable Domain Controllers
Compliance Management
Delegated Setup
Discovery Management
DnsUpdateProxy
Domain Admins
Domain Computers
Domain Controllers
Domain Guests
Domain Users
Enterprise Admins
Enterprise Key Admins
Enterprise Read-only Domain Controllers
Exchange Servers
Exchange Trusted Subsystem
Exchange Windows Permissions
ExchangeLegacyInterop
Group Policy Creator Owners
Help Desk
Hygiene Management
Key Admins
Managed Availability Servers
Organization Management
Privileged IT Accounts
Protected Users
Public Folder Management
Read-only Domain Controllers
Recipient Management
Records Management
Schema Admins
Security Administrator
Security Reader
Server Management
Service Accounts
test
UM Management
View-Only Organization Management
```
##### rpc group list local
```sh
└─$ net rpc group list local -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Cert Publishers
RAS and IAS Servers
Allowed RODC Password Replication Group
Denied RODC Password Replication Group
DnsAdmins
```
##### rpc group list builtin
```sh
└─$ net rpc group list builtin -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Account Operators
Pre-Windows 2000 Compatible Access
Incoming Forest Trust Builders
Windows Authorization Access Group
Terminal Server License Servers
Administrators
Users
Guests
Print Operators
Backup Operators
Replicator
Remote Desktop Users
Network Configuration Operators
Performance Monitor Users
Performance Log Users
Distributed COM Users
IIS_IUSRS
Cryptographic Operators
Event Log Readers
Certificate Service DCOM Access
RDS Remote Access Servers
RDS Endpoint Servers
RDS Management Servers
Hyper-V Administrators
Access Control Assistance Operators
Remote Management Users
System Managed Accounts Group
Storage Replica Administrators
Server Operators
```
#### group members
```sh
└─$ net rpc group members 'DOMAIN Admins' -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210 
HTB\Administrator
```
#### group add
```sh
└─$ net rpc group add hello -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Added group 'hello'.
```
#### group delete
```sh
└─$ net rpc group delete hello -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group rename
```sh
└─$ net rpc group rename hello hello1 -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group addmem
```sh
└─$ net rpc group addmem 'EXCHANGE WINDOWS PERMISSIONS' svc-alfresco -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group delmem
```sh
└─$ net rpc group delmem 'EXCHANGE WINDOWS PERMISSIONS' svc-alfresco -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
