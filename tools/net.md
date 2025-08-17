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
```sh
└─$ net rpc printer -U 'htb.local/svc-alfresco%s3rvice' -S 10.129.95.210
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
└─$ net rpc service status ADWS -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210
ADWS service is running.
Configuration details:
        Controls Accepted    = 0x5
        Service Type         = 0x10
        Start Type           = 0x2
        Error Control        = 0x1
        Tag ID               = 0x0
        Executable Path      = C:\Windows\ADWS\Microsoft.ActiveDirectory.WebServices.exe
        Load Order Group     = 
        Dependencies         = /
        Start Name           = LocalSystem
        Display Name         = Active Directory Web Services
```

### registry
#### registry enumerate
```sh
└─$ net rpc registry enumerate 'HKLM\' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
Keyname   = BCD00000000
Modtime   = Sun, 17 Aug 2025 05:46:35 EDT

Keyname   = HARDWARE
Modtime   = Sun, 17 Aug 2025 05:46:31 EDT

Keyname   = SAM
Modtime   = Sun, 17 Aug 2025 05:46:37 EDT

Keyname   = SECURITY
Modtime   = Sun, 17 Aug 2025 05:46:37 EDT

Keyname   = SOFTWARE
Modtime   = Sun, 17 Aug 2025 05:46:36 EDT

Keyname   = SYSTEM
Modtime   = Sun, 17 Aug 2025 05:46:31 EDT
```
#### registry getvalue
```sh
└─$ net rpc registry getvalue 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' 'VMware User Process' -U 'htb.local/administrator%32693b11e6aa90eb43d32c72a07ceea6' --pw-nt-hash -S 10.129.95.210 
Type       = REG_SZ
Value      = ""C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr"
```
