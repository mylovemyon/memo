## ads
### info
```sh
└─$ net ads info -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Failed to open /var/lib/samba/private/secrets.tdb
LDAP server: 10.129.95.210
LDAP server name: FOREST.htb.local
Workgroup: HTB
Realm: HTB.LOCAL
Bind Path: dc=HTB,dc=LOCAL
LDAP port: 389
Server time: Sun, 17 Aug 2025 12:55:20 EDT
KDC server: 10.129.95.210
Server time offset: 409
Last machine account password change: Wed, 31 Dec 1969 19:00:00 EST
```

### user
```sh
└─$ net ads user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Administrator
Guest
DefaultAccount
krbtgt
SM_2c8eef0a09b545acb
SM_ca8c2ed5bdab4dc9b
SM_75a538d3025e4db9a
SM_681f53d4942840e18
SM_1b41c9286325456bb
SM_9b69f1b9d2cc45549
SM_7c96b981967141ebb
SM_c75ee099d0a64c91b
SM_1ffab36a2f5f479cb
HealthMailboxc3d7722
HealthMailboxfc9daad
HealthMailboxc0a90c9
HealthMailbox670628e
HealthMailbox968e74d
HealthMailbox6ded678
HealthMailbox83d6781
HealthMailboxfd87238
HealthMailboxb01ac64
HealthMailbox7108a4e
HealthMailbox0659cc1
sebastien
lucinda
svc-alfresco
andy
mark
santi
```
#### user info
```sh
└─$ net ads user info administrator -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
wbcLookupSid: WBC_ERR_WINBIND_NOT_AVAILABLE
```
#### user add
```sh
└─$ net ads user add user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
User user added
```
#### user delete
```sh
└─$ net ads user delete user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
User user deleted
```

### group
#### group add
```sh
└─$ net ads group add user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Group user added
```
#### group delete
```sh
└─$ net ads group delete user -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210  
Group user deleted
```

### printer
#### printer search
```sh
└─$ net ads printer search -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
No results found
```

### search
```sh
└─$ net ads search 'sAMAccountName=administrator' 'distinguishedName' -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Got 1 replies

distinguishedName: CN=Administrator,CN=Users,DC=htb,DC=local
```

### dn
```sh
└─$ net ads dn 'CN=Administrator,CN=Users,DC=htb,DC=local' 'distinguishedName' -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Got 1 replies

distinguishedName: CN=Administrator,CN=Users,DC=htb,DC=local
```

### sid
```sh
└─$ net ads sid 'S-1-5-21-3072663084-364016917-1341370565-1147' -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Got 1 replies

objectClass: top
objectClass: person
objectClass: organizationalPerson
objectClass: user
cn: svc-alfresco
givenName: svc-alfresco
distinguishedName: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
instanceType: 4
whenCreated: 20190920005851.0Z
whenChanged: 20250818061717.0Z
displayName: svc-alfresco
uSNCreated: 26083
memberOf: CN=Service Accounts,OU=Security Groups,DC=htb,DC=local
uSNChanged: 5889911
name: svc-alfresco
objectGUID: 58a51302-4c7c-4686-9502-d3ada3afaef1
userAccountControl: 4260352
badPwdCount: 0
codePage: 0
countryCode: 0
badPasswordTime: 0
lastLogoff: 0
lastLogon: 132137105879311936
ads_pull_strvals: pull_utf8_talloc failed: Invalid argument
pwdLastSet: 133999714379251224
primaryGroupID: 513
objectSid: S-1-5-21-3072663084-364016917-1341370565-1147
adminCount: 1
accountExpires: 0
logonCount: 6
sAMAccountName: svc-alfresco
sAMAccountType: 805306368
userPrincipalName: svc-alfresco@htb.local
objectCategory: CN=Person,CN=Schema,CN=Configuration,DC=htb,DC=local
dSCorePropagationData: 20250818061739.0Z
dSCorePropagationData: 20250818061739.0Z
dSCorePropagationData: 20250818061739.0Z
dSCorePropagationData: 20250818061739.0Z
dSCorePropagationData: 16010101000000.0Z
lastLogonTimestamp: 132136663111826271
msDS-SupportedEncryptionTypes: 0
```

### workgroup
```sh
└─$ net ads workgroup -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210 
Workgroup: HTB
```

### lookup
```sh
└─$ net ads lookup -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Information for Domain Controller: 10.129.95.210

Response Type: LOGON_SAM_LOGON_RESPONSE_EX
GUID: dff0c71a-a949-4b26-8c7b-52e3e2cb6eab
Flags:
        Is a PDC:                                   yes
        Is a GC of the forest:                      yes
        Is an LDAP server:                          yes
        Supports DS:                                yes
        Is running a KDC:                           yes
        Is running time services:                   yes
        Is the closest DC:                          yes
        Is writable:                                yes
        Has a hardware clock:                       yes
        Is a non-domain NC serviced by LDAP server: no
        Is NT6 DC that has some secrets:            no
        Is NT6 DC that has all secrets:             yes
        Runs Active Directory Web Services:         yes
        Runs on Windows 2012 or later:              yes
        Runs on Windows 2012R2 or later:            yes
        Runs on Windows 2016 or later:              yes
        Has a DNS name:                             no
        Is a default NC:                            no
        Is the forest root:                         no
Forest: htb.local
Domain: htb.local
Domain Controller: FOREST.htb.local
Pre-Win2k Domain: HTB
Pre-Win2k Hostname: FOREST
Server Site Name: Default-First-Site-Name
Client Site Name: Default-First-Site-Name
NT Version: 5
LMNT Token: ffff
LM20 Token: ffff
```



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
##### group list global
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
##### group list local
```sh
└─$ net rpc group list local -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Cert Publishers
RAS and IAS Servers
Allowed RODC Password Replication Group
Denied RODC Password Replication Group
DnsAdmins
```
##### group list builtin
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
#### group addmem
```sh
└─$ net rpc group addmem 'EXCHANGE WINDOWS PERMISSIONS' svc-alfresco -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group delmem
```sh
└─$ net rpc group delmem 'EXCHANGE WINDOWS PERMISSIONS' svc-alfresco -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group add
```sh
└─$ net rpc group add hello -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Added group 'hello'.
```
#### group rename
```sh
└─$ net rpc group rename hello hello1 -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```
#### group delete
```sh
└─$ net rpc group delete hello -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210

```

### share
```sh
└─$ net rpc share -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210 
ADMIN$
C$
IPC$
NETLOGON
SYSVOL
```

### printer
#### printer list
```sh
└─$ net rpc printer list -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Could not initialise pipe spoolss. Error was NT_STATUS_OBJECT_NAME_NOT_FOUND
```
#### printer driver
```sh
└─$ net rpc printer driver -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
Could not initialise pipe spoolss. Error was NT_STATUS_OBJECT_NAME_NOT_FOUND
```

### service
#### service list
```sh
└─$ net rpc service list -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
ADWS                    "Active Directory Web Services"
AppIDSvc                "Application Identity"
AppMgmt                 "Application Management"
AppXSvc                 "AppX Deployment Service (AppXSVC)"
BFE                     "Base Filtering Engine"
BITS                    "Background Intelligent Transfer Service"
Browser                 "Computer Browser"
CertPropSvc             "Certificate Propagation"
ClipSVC                 "Client License Service (ClipSVC)"
COMSysApp               "COM+ System Application"
CoreMessagingRegistrar    "CoreMessaging"
CryptSvc                "Cryptographic Services"
DcomLaunch              "DCOM Server Process Launcher"
defragsvc               "Optimize drives"
DeviceInstall           "Device Install Service"
Dfs                     "DFS Namespace"
DFSR                    "DFS Replication"
Dhcp                    "DHCP Client"
diagnosticshub.standardcollector.service    "Microsoft (R) Diagnostics Hub Standard Collector Service"
DiagTrack               "Connected User Experiences and Telemetry"
DNS                     "DNS Server"
Dnscache                "DNS Client"
DPS                     "Diagnostic Policy Service"
DsRoleSvc               "DS Role Server"
EapHost                 "Extensible Authentication Protocol"
EFS                     "Encrypting File System (EFS)"
EventLog                "Windows Event Log"
EventSystem             "COM+ Event System"
fdPHost                 "Function Discovery Provider Host"
FontCache               "Windows Font Cache Service"
gpsvc                   "Group Policy Client"
hidserv                 "Human Interface Device Service"
HvHost                  "HV Host Service"
IKEEXT                  "IKE and AuthIP IPsec Keying Modules"
iphlpsvc                "IP Helper"
IsmServ                 "Intersite Messaging"
Kdc                     "Kerberos Key Distribution Center"
KdsSvc                  "Microsoft Key Distribution Service"
KeyIso                  "CNG Key Isolation"
KPSSVC                  "KDC Proxy Server service (KPS)"
KtmRm                   "KtmRm for Distributed Transaction Coordinator"
LanmanServer            "Server"
LanmanWorkstation       "Workstation"
lltdsvc                 "Link-Layer Topology Discovery Mapper"
lmhosts                 "TCP/IP NetBIOS Helper"
LSM                     "Local Session Manager"
MpsSvc                  "Windows Firewall"
MSDTC                   "Distributed Transaction Coordinator"
MSiSCSI                 "Microsoft iSCSI Initiator Service"
msiserver               "Windows Installer"
NcaSvc                  "Network Connectivity Assistant"
Netlogon                "Netlogon"
netprofm                "Network List Service"
NetSetupSvc             "Network Setup Service"
NetTcpPortSharing       "Net.Tcp Port Sharing Service"
NlaSvc                  "Network Location Awareness"
nsi                     "Network Store Interface Service"
NTDS                    "Active Directory Domain Services"
NtFrs                   "File Replication"
PerfHost                "Performance Counter DLL Host"
pla                     "Performance Logs & Alerts"
PlugPlay                "Plug and Play"
PolicyAgent             "IPsec Policy Agent"
Power                   "Power"
ProfSvc                 "User Profile Service"
RasMan                  "Remote Access Connection Manager"
RemoteAccess            "Routing and Remote Access"
RemoteRegistry          "Remote Registry"
RpcEptMapper            "RPC Endpoint Mapper"
RpcSs                   "Remote Procedure Call (RPC)"
RSoPProv                "Resultant Set of Policy Provider"
sacsvr                  "Special Administration Console Helper"
SamSs                   "Security Accounts Manager"
SCardSvr                "Smart Card"
ScDeviceEnum            "Smart Card Device Enumeration Service"
Schedule                "Task Scheduler"
SCPolicySvc             "Smart Card Removal Policy"
seclogon                "Secondary Logon"
SENS                    "System Event Notification Service"
SessionEnv              "Remote Desktop Configuration"
SharedAccess            "Internet Connection Sharing (ICS)"
smphost                 "Microsoft Storage Spaces SMP"
SNMPTRAP                "SNMP Trap"
Spooler                 "Print Spooler"
sppsvc                  "Software Protection"
SstpSvc                 "Secure Socket Tunneling Protocol Service"
StateRepository         "State Repository Service"
svsvc                   "Spot Verifier"
swprv                   "Microsoft Software Shadow Copy Provider"
SysMain                 "Superfetch"
SystemEventsBroker      "System Events Broker"
TermService             "Remote Desktop Services"
TieringEngineService    "Storage Tiers Management"
TimeBrokerSvc           "Time Broker"
TrustedInstaller        "Windows Modules Installer"
UALSVC                  "User Access Logging Service"
UmRdpService            "Remote Desktop Services UserMode Port Redirector"
UserManager             "User Manager"
UsoSvc                  "Update Orchestrator Service for Windows Update"
VaultSvc                "Credential Manager"
vds                     "Virtual Disk"
VGAuthService           "VMware Alias Manager and Ticket Service"
vmicguestinterface      "Hyper-V Guest Service Interface"
vmicheartbeat           "Hyper-V Heartbeat Service"
vmickvpexchange         "Hyper-V Data Exchange Service"
vmicrdv                 "Hyper-V Remote Desktop Virtualization Service"
vmicshutdown            "Hyper-V Guest Shutdown Service"
vmictimesync            "Hyper-V Time Synchronization Service"
vmicvmsession           "Hyper-V PowerShell Direct Service"
vmicvss                 "Hyper-V Volume Shadow Copy Requestor"
VMTools                 "VMware Tools"
vmvss                   "VMware Snapshot Provider"
VMwareCAFCommAmqpListener    "VMware CAF AMQP Communication Service"
VMwareCAFManagementAgentHost    "VMware CAF Management Agent Service"
VSS                     "Volume Shadow Copy"
W32Time                 "Windows Time"
WdiServiceHost          "Diagnostic Service Host"
WdiSystemHost           "Diagnostic System Host"
WdNisSvc                "Windows Defender Network Inspection Service"
Wecsvc                  "Windows Event Collector"
WerSvc                  "Windows Error Reporting Service"
WinDefend               "Windows Defender Service"
WinHttpAutoProxySvc     "WinHTTP Web Proxy Auto-Discovery Service"
Winmgmt                 "Windows Management Instrumentation"
WinRM                   "Windows Remote Management (WS-Management)"
wisvc                   "Windows Insider Service"
wmiApSrv                "WMI Performance Adapter"
wuauserv                "Windows Update"
wudfsvc                 "Windows Driver Foundation - User-mode Driver Framework"
```
#### service status
```sh
└─$ net rpc service status MpsSvc -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
MpsSvc service is running.
Configuration details:
        Controls Accepted    = 0x1
        Service Type         = 0x20
        Start Type           = 0x2
        Error Control        = 0x1
        Tag ID               = 0x0
        Executable Path      = C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
        Load Order Group     = NetworkProvider
        Dependencies         = mpsdrv/bfe/
        Start Name           = NT Authority\LocalService
        Display Name         = Windows Firewall
```
#### service start
```sh
└─$ net rpc service start MpsSvc -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
.
Successfully started service: MpsSvc
```
#### service stop
```sh
└─$ net rpc service stop MpsSvc -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210   
.
MpsSvc service is stopped.
```
#### service create
```sh
└─$ net rpc service create test test 'C:\Windows\System32\cmd.exe' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
Successfully created Service: test
                                                                                                                    
┌──(kali㉿kali)-[~]
└─$ net rpc service status test -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210                                   
test service is stopped.
Configuration details:
        Controls Accepted    = 0x0
        Service Type         = 0x10
        Start Type           = 0x3
        Error Control        = 0x1
        Tag ID               = 0x0
        Executable Path      = C:\Windows\System32\cmd.exe
        Load Order Group     = 
        Dependencies         = /
        Start Name           = LocalSystem
        Display Name         = test
```
#### service delete
```sh
└─$ net rpc service delete test -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210    
Successfully deleted Service: test
```

### registry
#### registry enumerate
```sh
└─$ net rpc registry enumerate 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
Valuename  = VMware User Process
Type       = REG_SZ
Value      = ""C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr"
```
#### registry getvalue
```sh
└─$ net rpc registry getvalue 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'VMware User Process' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
Type       = REG_SZ
Value      = ""C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr"
```
#### registry getvalueraw
```sh
└─$ net rpc registry getvalueraw 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'VMware User Process' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
"C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr
```
#### registry createkey
```sh
└─$ net rpc registry createkey 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run\test' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
createkey created HKLM\Software\Microsoft\Windows\CurrentVersion\Run\test
```
#### registry deletekey
```sh
└─$ net rpc registry deletekey 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run\test' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210

```
#### registry 
```sh
#  typeは、sz、multi_sz、dwordのうちのどれかが選べる
└─$ net rpc registry setvalue 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'test' 'SZ' 'C:\Windows\System32\cmd.exe' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 

└─$ net rpc registry getvalue 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'test' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210                                
Type       = REG_SZ
Value      = "C:\Windows\System32\cmd.exe"
```
#### 
```sh
└─$ net rpc registry deletevalue 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'test' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210

```
#### registry export
```sh
└─$ net rpc registry export 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' reg.txt -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
                                                                                                                    
└─$ cat reg.txt               
Windows Registry Editor Version 5.00

[HKLM\Software\Microsoft\Windows\CurrentVersion\Run]
"VMware User Process"="\"C:\\Program Files\\VMware\\VMware Tools\\vmtoolsd.exe\" -n vmusr"
;Local Variables:
;coding: UTF-8
;End:
```
#### registry save
```sh
└─$ net rpc registry save 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'C:\Users\Public\reg' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 

```

### shell
```sh
└─$ net rpc shell -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
Talking to domain HTB (S-1-5-21-3072663084-364016917-1341370565)
net rpc> help
info            Print information about the domain connected to
rights          List/Grant/Revoke user rights
share           List/Add/Remove etc shares
user            List/Add/Remove user info
account         Show/Change account policy settings
```
#### shell info
```sh
net rpc> info
Domain Name: HTB
Domain SID: S-1-5-21-3072663084-364016917-1341370565
Sequence number: 1
Num users: 106
Num domain groups: 0
Num local groups: 0
```
####  shell share
##### shell share list
```sh
net rpc> share list
ADMIN$
C$
IPC$
NETLOGON
SYSVOL
```
##### shell share info
```sh
net rpc> share info 'C$'
Name:     C$
Comment:  Default share
Path:     C:\
Password: (null)
```
#### shell user
##### shell user list
```sh
net rpc> user list
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
user
```
##### shell user info
```sh
net rpc> user info administrator
Enterprise Admins
Organization Management
Domain Users
Group Policy Creator Owners
Domain Admins
Schema Admins
```
##### shell user show
```sh
net rpc> user show administrator
user rid: 500, group rid: 513
```
##### shell user edit
```sh
net rpc> user edit fullname administrator
Administrator's fullname: [Administrator]

net rpc> user edit homedir administrator
Administrator's homedir: []

net rpc> user edit homedrive administrator
Administrator's homedrive: []

net rpc> user edit logonscript administrator
Administrator's logonscript: []

net rpc> user edit profilepath administrator
Administrator's profilepath: []

net rpc> user edit description administrator
Administrator's description: [Built-in account for administering the computer/domain]

net rpc> user edit disabled administrator
Administrator's disabled flag: no

net rpc> user edit autolock administrator
Administrator's autolock flag: no

net rpc> user edit pwnotreq administrator
Administrator's pwnotreq flag: no

net rpc> user edit pwnoexp administrator
Administrator's pwnoexp flag: no

net rpc> user edit pwnoexp administrator yes
Set Administrator's pwnoexp flag from [no] to [yes]
net rpc> user edit pwnoexp administrator
Administrator's pwnoexp flag: yes
```

#### account
##### account show
```sh
net rpc> account show
Minimum password length: 7
Password history length: 24
Minimum password age: 86400 seconds
Maximum password age: not set
Bad logon attempts: 0
Disconnect users when logon hours expire: no
User must logon to change password: no
```
##### account badpw
```sh
net rpc> account badpw 0
Setting bad password count to 0
```
##### account resetduration
```sh
net rpc> account resetduration 0
Setting bad password reset duration to 0 seconds
```
##### account lockduration
```sh
net rpc> account lockduration 0
Setting lockout duration to 0 seconds
```
##### account minpwage
```sh
net rpc> account minpwage 0
Setting minimum password age to 0 seconds
```
##### account maxpwage
```sh
net rpc> account maxpwage 0
Setting maximum password age to 0 seconds
```
##### account minpwlen
```sh
net rpc> account minpwlen 0
Setting minimum password length to 0
```
##### account pwhistlen
```sh
net rpc> account pwhistlen 0
Setting password history length to 0
```
