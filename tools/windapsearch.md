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
