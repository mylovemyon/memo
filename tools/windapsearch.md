### metadata
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m metadata -v 
INFO[2025-08-28T08:29:13-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:29:14-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:29:14-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:29:14-04:00] sending LDAP search request                   attributes="[defaultNamingContext domainFunctionality forestFunctionality domainControllerFunctionality dnsHostName]" filter="(objectClass=*)" package=ldapsession
defaultNamingContext: DC=htb,DC=local
dnsHostName: FOREST.htb.local
domainFunctionality: 7
forestFunctionality: 7
domainControllerFunctionality: 7
```



### gpos
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m gpos -v
INFO[2025-08-28T08:09:14-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:09:15-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:09:16-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:09:16-04:00] sending LDAP search request                   attributes="[displayName gPCFileSysPath]" filter="(objectClass=groupPolicyContainer)" package=ldapsession
dn: CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=htb,DC=local
displayName: Default Domain Policy
gPCFileSysPath: \\htb.local\sysvol\htb.local\Policies\{31B2F340-016D-11D2-945F-00C04FB984F9}

dn: CN={6AC1786C-016F-11D2-945F-00C04fB984F9},CN=Policies,CN=System,DC=htb,DC=local
displayName: Default Domain Controllers Policy
gPCFileSysPath: \\htb.local\sysvol\htb.local\Policies\{6AC1786C-016F-11D2-945F-00C04fB984F9}
INFO[2025-08-28T08:09:16-04:00] Received page 1 with 2 LDAP entries...        package=ldapsession
```



### computers
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m computers -v
INFO[2025-08-28T08:11:52-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:11:53-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:11:54-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:11:54-04:00] sending LDAP search request                   attributes="[cn dNSHostName operatingSystem operatingSystemVersion operatingSystemServicePack]" filter="(objectClass=Computer)" package=ldapsession
INFO[2025-08-28T08:11:54-04:00] Received page 1 with 2 LDAP entries...        package=ldapsession
dn: CN=FOREST,OU=Domain Controllers,DC=htb,DC=local
cn: FOREST
operatingSystem: Windows Server 2016 Standard
operatingSystemVersion: 10.0 (14393)
dNSHostName: FOREST.htb.local

dn: CN=EXCH01,CN=Computers,DC=htb,DC=local
cn: EXCH01
operatingSystem: Windows Server 2016 Standard
operatingSystemVersion: 10.0 (14393)
dNSHostName: EXCH01.htb.local
```



### admin-objects
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m admin-objects -v         
INFO[2025-08-28T08:12:26-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:12:27-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:12:27-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:12:27-04:00] sending LDAP search request                   attributes="[cn]" filter="(adminCount=1)" package=ldapsession
dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator

dn: CN=Schema Admins,CN=Users,DC=htb,DC=local
cn: Schema Admins

dn: CN=Enterprise Admins,CN=Users,DC=htb,DC=local
cn: Enterprise Admins

dn: CN=Read-only Domain Controllers,CN=Users,DC=htb,DC=local
cn: Read-only Domain Controllers

dn: CN=krbtgt,CN=Users,DC=htb,DC=local
cn: krbtgt

dn: CN=Domain Controllers,CN=Users,DC=htb,DC=local
cn: Domain Controllers

dn: CN=Domain Admins,CN=Users,DC=htb,DC=local
cn: Domain Admins

dn: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
cn: svc-alfresco

dn: CN=Service Accounts,OU=Security Groups,DC=htb,DC=local
cn: Service Accounts

dn: CN=Backup Operators,CN=Builtin,DC=htb,DC=local
cn: Backup Operators

dn: CN=Privileged IT Accounts,OU=Security Groups,DC=htb,DC=local
cn: Privileged IT Accounts

dn: CN=Account Operators,CN=Builtin,DC=htb,DC=local
cn: Account Operators

dn: CN=Administrators,CN=Builtin,DC=htb,DC=local
cn: Administrators

dn: CN=Print Operators,CN=Builtin,DC=htb,DC=local
cn: Print Operators

dn: CN=Replicator,CN=Builtin,DC=htb,DC=local
cn: Replicator

dn: CN=Server Operators,CN=Builtin,DC=htb,DC=local
cn: Server Operators
INFO[2025-08-28T08:12:28-04:00] Received page 1 with 16 LDAP entries...       package=ldapsession
```



### domain-admins 
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m domain-admins -v
INFO[2025-08-28T08:11:26-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:11:27-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:11:28-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:11:28-04:00] sending LDAP search request                   attributes="[cn sAMAccountName]" filter="(&(objectClass=user)(|(memberof:1.2.840.113556.1.4.1941:=CN=Domain Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain Administrators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Administrators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen Administratoren,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen-Administratoren,CN=Users,DC=htb,DC=local)))" package=ldapsession
INFO[2025-08-28T08:11:28-04:00] Received page 1 with 1 LDAP entries...        package=ldapsession
dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator
sAMAccountName: Administrator
```



### groups
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m groups -v
INFO[2025-08-28T08:18:17-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:18:18-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:18:19-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:18:19-04:00] sending LDAP search request                   attributes="[cn]" filter="(objectcategory=group)" package=ldapsession
dn: CN=Backup Operators,CN=Builtin,DC=htb,DC=local
cn: Backup Operators

dn: CN=Replicator,CN=Builtin,DC=htb,DC=local
cn: Replicator

dn: CN=Administrators,CN=Builtin,DC=htb,DC=local
cn: Administrators

dn: CN=Users,CN=Builtin,DC=htb,DC=local
cn: Users

dn: CN=Guests,CN=Builtin,DC=htb,DC=local
cn: Guests

dn: CN=Print Operators,CN=Builtin,DC=htb,DC=local
cn: Print Operators

dn: CN=Remote Desktop Users,CN=Builtin,DC=htb,DC=local
cn: Remote Desktop Users

dn: CN=IIS_IUSRS,CN=Builtin,DC=htb,DC=local
cn: IIS_IUSRS

dn: CN=Cryptographic Operators,CN=Builtin,DC=htb,DC=local
cn: Cryptographic Operators

dn: CN=Distributed COM Users,CN=Builtin,DC=htb,DC=local
cn: Distributed COM Users

dn: CN=Performance Log Users,CN=Builtin,DC=htb,DC=local
cn: Performance Log Users

dn: CN=Network Configuration Operators,CN=Builtin,DC=htb,DC=local
cn: Network Configuration Operators

dn: CN=Performance Monitor Users,CN=Builtin,DC=htb,DC=local
cn: Performance Monitor Users

dn: CN=Event Log Readers,CN=Builtin,DC=htb,DC=local
cn: Event Log Readers

dn: CN=Hyper-V Administrators,CN=Builtin,DC=htb,DC=local
cn: Hyper-V Administrators

dn: CN=Certificate Service DCOM Access,CN=Builtin,DC=htb,DC=local
cn: Certificate Service DCOM Access

dn: CN=RDS Remote Access Servers,CN=Builtin,DC=htb,DC=local
cn: RDS Remote Access Servers

dn: CN=RDS Endpoint Servers,CN=Builtin,DC=htb,DC=local
cn: RDS Endpoint Servers

dn: CN=RDS Management Servers,CN=Builtin,DC=htb,DC=local
cn: RDS Management Servers

dn: CN=Access Control Assistance Operators,CN=Builtin,DC=htb,DC=local
cn: Access Control Assistance Operators

dn: CN=Remote Management Users,CN=Builtin,DC=htb,DC=local
cn: Remote Management Users

dn: CN=System Managed Accounts Group,CN=Builtin,DC=htb,DC=local
cn: System Managed Accounts Group

dn: CN=Enterprise Admins,CN=Users,DC=htb,DC=local
cn: Enterprise Admins

dn: CN=Domain Computers,CN=Users,DC=htb,DC=local
cn: Domain Computers

dn: CN=Cert Publishers,CN=Users,DC=htb,DC=local
cn: Cert Publishers

dn: CN=Storage Replica Administrators,CN=Builtin,DC=htb,DC=local
cn: Storage Replica Administrators

dn: CN=Domain Controllers,CN=Users,DC=htb,DC=local
cn: Domain Controllers

dn: CN=Schema Admins,CN=Users,DC=htb,DC=local
cn: Schema Admins

dn: CN=Domain Admins,CN=Users,DC=htb,DC=local
cn: Domain Admins

dn: CN=Server Operators,CN=Builtin,DC=htb,DC=local
cn: Server Operators

dn: CN=Account Operators,CN=Builtin,DC=htb,DC=local
cn: Account Operators

dn: CN=Domain Users,CN=Users,DC=htb,DC=local
cn: Domain Users

dn: CN=Domain Guests,CN=Users,DC=htb,DC=local
cn: Domain Guests

dn: CN=Group Policy Creator Owners,CN=Users,DC=htb,DC=local
cn: Group Policy Creator Owners

dn: CN=RAS and IAS Servers,CN=Users,DC=htb,DC=local
cn: RAS and IAS Servers

dn: CN=Pre-Windows 2000 Compatible Access,CN=Builtin,DC=htb,DC=local
cn: Pre-Windows 2000 Compatible Access

dn: CN=Denied RODC Password Replication Group,CN=Users,DC=htb,DC=local
cn: Denied RODC Password Replication Group

dn: CN=Read-only Domain Controllers,CN=Users,DC=htb,DC=local
cn: Read-only Domain Controllers

dn: CN=Incoming Forest Trust Builders,CN=Builtin,DC=htb,DC=local
cn: Incoming Forest Trust Builders

dn: CN=Windows Authorization Access Group,CN=Builtin,DC=htb,DC=local
cn: Windows Authorization Access Group

dn: CN=Terminal Server License Servers,CN=Builtin,DC=htb,DC=local
cn: Terminal Server License Servers

dn: CN=Allowed RODC Password Replication Group,CN=Users,DC=htb,DC=local
cn: Allowed RODC Password Replication Group

dn: CN=Enterprise Read-only Domain Controllers,CN=Users,DC=htb,DC=local
cn: Enterprise Read-only Domain Controllers

dn: CN=DnsAdmins,CN=Users,DC=htb,DC=local
cn: DnsAdmins

dn: CN=DnsUpdateProxy,CN=Users,DC=htb,DC=local
cn: DnsUpdateProxy

dn: CN=Cloneable Domain Controllers,CN=Users,DC=htb,DC=local
cn: Cloneable Domain Controllers

dn: CN=Protected Users,CN=Users,DC=htb,DC=local
cn: Protected Users

dn: CN=Key Admins,CN=Users,DC=htb,DC=local
cn: Key Admins

dn: CN=Enterprise Key Admins,CN=Users,DC=htb,DC=local
cn: Enterprise Key Admins

dn: CN=Organization Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Organization Management

dn: CN=Help Desk,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Help Desk

dn: CN=Records Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Records Management

dn: CN=Recipient Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Recipient Management

dn: CN=View-Only Organization Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: View-Only Organization Management

dn: CN=Public Folder Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Public Folder Management

dn: CN=UM Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: UM Management

dn: CN=Discovery Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Discovery Management

dn: CN=Security Reader,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Security Reader

dn: CN=Security Administrator,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Security Administrator

dn: CN=Server Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Server Management

dn: CN=Delegated Setup,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Delegated Setup

dn: CN=Hygiene Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Hygiene Management

dn: CN=Compliance Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Compliance Management

dn: CN=Exchange Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Exchange Servers

dn: CN=Exchange Install Domain Servers,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: Exchange Install Domain Servers

dn: CN=Service Accounts,OU=Security Groups,DC=htb,DC=local
cn: Service Accounts

dn: CN=Exchange Trusted Subsystem,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Exchange Trusted Subsystem

dn: CN=Managed Availability Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Managed Availability Servers

dn: CN=Exchange Windows Permissions,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: Exchange Windows Permissions

dn: CN=ExchangeLegacyInterop,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
cn: ExchangeLegacyInterop

dn: CN=Privileged IT Accounts,OU=Security Groups,DC=htb,DC=local
cn: Privileged IT Accounts
INFO[2025-08-28T08:18:20-04:00] Received page 1 with 72 LDAP entries...       package=ldapsession

dn: CN=test,OU=Security Groups,DC=htb,DC=local
cn: test
```



### members
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m members -g 'CN=Administrators,CN=Builtin,DC=htb,DC=local' -r -v
INFO[2025-08-28T08:21:24-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:21:25-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:21:26-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:21:26-04:00] sending LDAP search request                   attributes="[cn sAMAccountName]" filter="(memberof:1.2.840.113556.1.4.1941:=CN=Administrators,CN=Builtin,DC=htb,DC=local)" package=ldapsession
INFO[2025-08-28T08:21:26-04:00] Received page 1 with 3 LDAP entries...        package=ldapsession
dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator
sAMAccountName: Administrator

dn: CN=Enterprise Admins,CN=Users,DC=htb,DC=local
cn: Enterprise Admins
sAMAccountName: Enterprise Admins

dn: CN=Domain Admins,CN=Users,DC=htb,DC=local
cn: Domain Admins
sAMAccountName: Domain Admins


└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m members -s administrators -v
INFO[2025-08-28T08:28:19-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:28:20-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:28:21-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:28:21-04:00] sending LDAP search request                   attributes="[]" filter="(&((objectcategory=group))(anr=administrators))" package=ldapsession
[+] Using group: CN=Administrators,CN=Builtin,DC=htb,DC=local

INFO[2025-08-28T08:28:21-04:00] sending LDAP search request                   attributes="[cn sAMAccountName]" filter="(memberOf=CN=Administrators,CN=Builtin,DC=htb,DC=local)" package=ldapsession
INFO[2025-08-28T08:28:22-04:00] Received page 1 with 3 LDAP entries...        package=ldapsession
dn: CN=Domain Admins,CN=Users,DC=htb,DC=local
cn: Domain Admins
sAMAccountName: Domain Admins

dn: CN=Enterprise Admins,CN=Users,DC=htb,DC=local
cn: Enterprise Admins
sAMAccountName: Enterprise Admins

dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator
sAMAccountName: Administrator
```



### users
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m users -v
INFO[2025-08-28T09:03:37-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T09:03:39-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T09:03:39-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T09:03:39-04:00] sending LDAP search request                   attributes="[cn sAMAccountName userPrincipalName]" filter="(objectcategory=user)" package=ldapsession
dn: CN=Exchange Online-ApplicationAccount,CN=Users,DC=htb,DC=local
cn: Exchange Online-ApplicationAccount
sAMAccountName: $331000-VK4ADACQNUCA
userPrincipalName: Exchange_Online-ApplicationAccount@htb.local

dn: CN=SystemMailbox{1f05a927-89c0-4725-adca-4527114196a1},CN=Users,DC=htb,DC=local
cn: SystemMailbox{1f05a927-89c0-4725-adca-4527114196a1}
sAMAccountName: SM_2c8eef0a09b545acb
userPrincipalName: SystemMailbox{1f05a927-89c0-4725-adca-4527114196a1}@htb.local

dn: CN=DefaultAccount,CN=Users,DC=htb,DC=local
cn: DefaultAccount
sAMAccountName: DefaultAccount

dn: CN=krbtgt,CN=Users,DC=htb,DC=local
cn: krbtgt
sAMAccountName: krbtgt

dn: CN=Guest,CN=Users,DC=htb,DC=local
cn: Guest
sAMAccountName: Guest

dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator
sAMAccountName: Administrator
userPrincipalName: Administrator@htb.local

dn: CN=SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c},CN=Users,DC=htb,DC=local
cn: SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}
sAMAccountName: SM_ca8c2ed5bdab4dc9b
userPrincipalName: SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}@htb.local

dn: CN=DiscoverySearchMailbox {D919BA05-46A6-415f-80AD-7E09334BB852},CN=Users,DC=htb,DC=local
cn: DiscoverySearchMailbox {D919BA05-46A6-415f-80AD-7E09334BB852}
sAMAccountName: SM_681f53d4942840e18
userPrincipalName: DiscoverySearchMailbox {D919BA05-46A6-415f-80AD-7E09334BB852}@htb.local

dn: CN=SystemMailbox{2CE34405-31BE-455D-89D7-A7C7DA7A0DAA},CN=Users,DC=htb,DC=local
cn: SystemMailbox{2CE34405-31BE-455D-89D7-A7C7DA7A0DAA}
sAMAccountName: SM_c75ee099d0a64c91b
userPrincipalName: SystemMailbox{2CE34405-31BE-455D-89D7-A7C7DA7A0DAA}@htb.local

dn: CN=SystemMailbox{e0dc1c29-89c3-4034-b678-e6c29d823ed9},CN=Users,DC=htb,DC=local
cn: SystemMailbox{e0dc1c29-89c3-4034-b678-e6c29d823ed9}
sAMAccountName: SM_75a538d3025e4db9a
userPrincipalName: SystemMailbox{e0dc1c29-89c3-4034-b678-e6c29d823ed9}@htb.local

dn: CN=SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9},CN=Users,DC=htb,DC=local
cn: SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}
sAMAccountName: SM_1ffab36a2f5f479cb
userPrincipalName: SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}@htb.local

dn: CN=HealthMailboxfc9daad117b84fe08b081886bd8a5a50,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailboxfc9daad117b84fe08b081886bd8a5a50
sAMAccountName: HealthMailboxfc9daad
userPrincipalName: HealthMailboxfc9daad117b84fe08b081886bd8a5a50@htb.local

dn: CN=HealthMailboxc0a90c97d4994429b15003d6a518f3f5,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailboxc0a90c97d4994429b15003d6a518f3f5
sAMAccountName: HealthMailboxc0a90c9
userPrincipalName: HealthMailboxc0a90c97d4994429b15003d6a518f3f5@htb.local

dn: CN=HealthMailboxc3d7722415ad41a5b19e3e00e165edbe,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailboxc3d7722415ad41a5b19e3e00e165edbe
sAMAccountName: HealthMailboxc3d7722
userPrincipalName: HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local

dn: CN=SystemMailbox{D0E409A0-AF9B-4720-92FE-AAC869B0D201},CN=Users,DC=htb,DC=local
cn: SystemMailbox{D0E409A0-AF9B-4720-92FE-AAC869B0D201}
sAMAccountName: SM_7c96b981967141ebb
userPrincipalName: SystemMailbox{D0E409A0-AF9B-4720-92FE-AAC869B0D201}@htb.local

dn: CN=Migration.8f3e7716-2011-43e4-96b1-aba62d229136,CN=Users,DC=htb,DC=local
cn: Migration.8f3e7716-2011-43e4-96b1-aba62d229136
sAMAccountName: SM_1b41c9286325456bb
userPrincipalName: Migration.8f3e7716-2011-43e4-96b1-aba62d229136@htb.local

dn: CN=FederatedEmail.4c1f4d8b-8179-4148-93bf-00a95fa1e042,CN=Users,DC=htb,DC=local
cn: FederatedEmail.4c1f4d8b-8179-4148-93bf-00a95fa1e042
sAMAccountName: SM_9b69f1b9d2cc45549
userPrincipalName: FederatedEmail.4c1f4d8b-8179-4148-93bf-00a95fa1e042@htb.local

dn: CN=HealthMailbox670628ec4dd64321acfdf6e67db3a2d8,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox670628ec4dd64321acfdf6e67db3a2d8
sAMAccountName: HealthMailbox670628e
userPrincipalName: HealthMailbox670628ec4dd64321acfdf6e67db3a2d8@htb.local

dn: CN=HealthMailboxb01ac647a64648d2a5fa21df27058a24,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailboxb01ac647a64648d2a5fa21df27058a24
sAMAccountName: HealthMailboxb01ac64
userPrincipalName: HealthMailboxb01ac647a64648d2a5fa21df27058a24@htb.local

dn: CN=HealthMailbox6ded67848a234577a1756e072081d01f,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox6ded67848a234577a1756e072081d01f
sAMAccountName: HealthMailbox6ded678
userPrincipalName: HealthMailbox6ded67848a234577a1756e072081d01f@htb.local

dn: CN=HealthMailbox7108a4e350f84b32a7a90d8e718f78cf,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox7108a4e350f84b32a7a90d8e718f78cf
sAMAccountName: HealthMailbox7108a4e
userPrincipalName: HealthMailbox7108a4e350f84b32a7a90d8e718f78cf@htb.local

dn: CN=HealthMailbox968e74dd3edb414cb4018376e7dd95ba,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox968e74dd3edb414cb4018376e7dd95ba
sAMAccountName: HealthMailbox968e74d
userPrincipalName: HealthMailbox968e74dd3edb414cb4018376e7dd95ba@htb.local

dn: CN=HealthMailbox83d6781be36b4bbf8893b03c2ee379ab,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox83d6781be36b4bbf8893b03c2ee379ab
sAMAccountName: HealthMailbox83d6781
userPrincipalName: HealthMailbox83d6781be36b4bbf8893b03c2ee379ab@htb.local

dn: CN=HealthMailboxfd87238e536e49e08738480d300e3772,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailboxfd87238e536e49e08738480d300e3772
sAMAccountName: HealthMailboxfd87238
userPrincipalName: HealthMailboxfd87238e536e49e08738480d300e3772@htb.local

dn: CN=HealthMailbox0659cc188f4c4f9f978f6c2142c4181e,CN=Monitoring Mailboxes,CN=Microsoft Exchange System Objects,DC=htb,DC=local
cn: HealthMailbox0659cc188f4c4f9f978f6c2142c4181e
sAMAccountName: HealthMailbox0659cc1
userPrincipalName: HealthMailbox0659cc188f4c4f9f978f6c2142c4181e@htb.local

dn: CN=Sebastien Caron,OU=Exchange Administrators,OU=Information Technology,OU=Employees,DC=htb,DC=local
cn: Sebastien Caron
sAMAccountName: sebastien
userPrincipalName: sebastien@htb.local

dn: CN=Lucinda Berger,OU=IT Management,OU=Information Technology,OU=Employees,DC=htb,DC=local
cn: Lucinda Berger
sAMAccountName: lucinda
userPrincipalName: lucinda@htb.local

dn: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
cn: svc-alfresco
sAMAccountName: svc-alfresco
userPrincipalName: svc-alfresco@htb.local

dn: CN=Andy Hislip,OU=Helpdesk,OU=Information Technology,OU=Employees,DC=htb,DC=local
cn: Andy Hislip
sAMAccountName: andy
userPrincipalName: andy@htb.local

dn: CN=Mark Brandt,OU=Sysadmins,OU=Information Technology,OU=Employees,DC=htb,DC=local
cn: Mark Brandt
sAMAccountName: mark
userPrincipalName: mark@htb.local
INFO[2025-08-28T09:03:40-04:00] Received page 1 with 31 LDAP entries...       package=ldapsession

dn: CN=Santi Rodriguez,OU=Developers,OU=Information Technology,OU=Employees,DC=htb,DC=local
cn: Santi Rodriguez
sAMAccountName: santi
userPrincipalName: santi@htb.local
```
### privileged-users
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m privileged-users -v
INFO[2025-08-28T08:30:24-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:30:25-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:30:26-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:30:26-04:00] sending LDAP search request                   attributes="[cn sAMAccountName]" filter="(&(objectClass=user)(|(memberof:1.2.840.113556.1.4.1941:=CN=Administrators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Enterprise Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Schema Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Account Operators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Backup Operators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Server Management,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Konten-Operatoren,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Sicherungs-Operatoren,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Server-Operatoren,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Schema-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain Administrators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Administrators,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domain-Admins,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen Administratoren,CN=Users,DC=htb,DC=local)(memberof:1.2.840.113556.1.4.1941:=CN=Domänen-Administratoren,CN=Users,DC=htb,DC=local)))" package=ldapsession
INFO[2025-08-28T08:30:26-04:00] Received page 1 with 1 LDAP entries...        package=ldapsession
dn: CN=Administrator,CN=Users,DC=htb,DC=local
cn: Administrator
sAMAccountName: Administrator
```



### unconstrained
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m unconstrained -v
INFO[2025-08-28T08:53:10-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:53:12-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:53:12-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:53:12-04:00] sending LDAP search request                   attributes="[cn sAMAccountName]" filter="(userAccountControl:1.2.840.113556.1.4.803:=524288)" package=ldapsession
INFO[2025-08-28T08:53:13-04:00] Received page 1 with 1 LDAP entries...        package=ldapsession
dn: CN=FOREST,OU=Domain Controllers,DC=htb,DC=local
cn: FOREST
sAMAccountName: FOREST$
```



### user-spns
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m user-spns -v
INFO[2025-08-28T08:59:28-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:59:29-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:59:30-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:59:30-04:00] sending LDAP search request                   attributes="[cn sAMAccountName servicePrincipalName]" filter="(&(&(servicePrincipalName=*)(UserAccountControl:1.2.840.113556.1.4.803:=512))(!(UserAccountControl:1.2.840.113556.1.4.803:=2)))" package=ldapsession
INFO[2025-08-28T08:59:30-04:00] Received page 1 with 0 LDAP entries...        package=ldapsession
```



### search
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m search -s administrator --attrs sAMAccountName -v
INFO[2025-08-28T08:37:20-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T08:37:21-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T08:37:22-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T08:37:22-04:00] sending LDAP search request                   attributes="[distinguishedName]" filter="(anr=administrator)" package=ldapsession
What DN do you want to use?

1. CN=Administrator,CN=Users,DC=htb,DC=local
2. CN=Administrators,CN=Builtin,DC=htb,DC=local

Enter a number: 1

INFO[2025-08-28T08:37:24-04:00] sending LDAP search request                   attributes="[sAMAccountName]" filter="(cn=*)" package=ldapsession
INFO[2025-08-28T08:37:25-04:00] Received page 1 with 1 LDAP entries...        package=ldapsession
dn: CN=Administrator,CN=Users,DC=htb,DC=local
sAMAccountName: Administrator
```



### custom
```sh
└─$ ./windapsearch-linux-amd64 --dc 10.129.125.30 -u 'svc-alfresco@htb.local' -p s3rvice -m custom --filter '(&(servicePrincipalName=*)(UserAccountControl:1.2.840.113556.1.4.803:=512))' --attrs UserAccountControl,sAMAccountName -v
INFO[2025-08-28T09:09:20-04:00] Saving output to STDOUT                       package=windapsearch
INFO[2025-08-28T09:09:21-04:00] successful bind to "ldap://10.129.125.30:389" as "svc-alfresco@htb.local"  package=ldapsession
INFO[2025-08-28T09:09:22-04:00] retrieved default naming context: "DC=htb,DC=local"  package=ldapsession
INFO[2025-08-28T09:09:22-04:00] sending LDAP search request                   attributes="[UserAccountControl sAMAccountName]" filter="(&(servicePrincipalName=*)(UserAccountControl:1.2.840.113556.1.4.803:=512))" package=ldapsession
INFO[2025-08-28T09:09:22-04:00] Received page 1 with 1 LDAP entries...        package=ldapsession
dn: CN=krbtgt,CN=Users,DC=htb,DC=local
userAccountControl: 514
sAMAccountName: krbtgt
```
