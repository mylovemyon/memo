```sh
└─$ python3.13 silenthound.py -u svc-alfresco -p s3rvice -g -n -k --kerberoast 10.129.125.30 htb.local


   _____ _ _            _   _    _                       _ 
  / ____(_) |          | | | |  | |                     | |
 | (___  _| | ___ _ __ | |_| |__| | ___  _   _ _ __   __| |
  \___ \| | |/ _ \ '_ \| __|  __  |/ _ \| | | | '_ \ / _` |
  ____) | | |  __/ | | | |_| |  | | (_) | |_| | | | | (_| |
 |_____/|_|_|\___|_| |_|\__|_|  |_|\___/ \__,_|_| |_|\__,_|


                author: Nick Swink aka c0rnbread

                company: Layer 8 Security <layer8security.com>

---------------------------------------------------------------------------

[*] Located LDAP cache '.htb-local.pickle'. Delete cache to run updated query...
[*] Resolving hostnames |████████████████████████████████████████| 2/2 [100%] in 0.3s (5.43/s) 
[+] Hosts [2]
FOREST 
EXCH01 


[+] Domain Admins [1]
Administrator@htb.local


[+] Domain Users [31]
krbtgt
DefaultAccount
Guest
Administrator@htb.local
SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}@htb.local
SystemMailbox{2CE34405-31BE-455D-89D7-A7C7DA7A0DAA}@htb.local
SystemMailbox{D0E409A0-AF9B-4720-92FE-AAC869B0D201}@htb.local
FederatedEmail.4c1f4d8b-8179-4148-93bf-00a95fa1e042@htb.local
Migration.8f3e7716-2011-43e4-96b1-aba62d229136@htb.local
DiscoverySearchMailbox {D919BA05-46A6-415f-80AD-7E09334BB852}@htb.local
SystemMailbox{e0dc1c29-89c3-4034-b678-e6c29d823ed9}@htb.local
SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}@htb.local
SystemMailbox{1f05a927-89c0-4725-adca-4527114196a1}@htb.local
Exchange_Online-ApplicationAccount@htb.local
mark@htb.local
andy@htb.local
lucinda@htb.local
santi@htb.local
sebastien@htb.local
svc-alfresco@htb.local
HealthMailbox0659cc188f4c4f9f978f6c2142c4181e@htb.local
HealthMailbox7108a4e350f84b32a7a90d8e718f78cf@htb.local
HealthMailboxb01ac647a64648d2a5fa21df27058a24@htb.local
HealthMailboxfd87238e536e49e08738480d300e3772@htb.local
HealthMailbox83d6781be36b4bbf8893b03c2ee379ab@htb.local
HealthMailbox6ded67848a234577a1756e072081d01f@htb.local
HealthMailbox968e74dd3edb414cb4018376e7dd95ba@htb.local
HealthMailbox670628ec4dd64321acfdf6e67db3a2d8@htb.local
HealthMailboxc0a90c97d4994429b15003d6a518f3f5@htb.local
HealthMailboxfc9daad117b84fe08b081886bd8a5a50@htb.local
HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local


[+] Descriptions [1]
Administrator@htb.local - Built-in account for administering the computer/domain


[+] Group Memberships Found [22]
CN=Group Policy Creator Owners,CN=Users,DC=htb,DC=local
Administrator@htb.local


CN=Domain Admins,CN=Users,DC=htb,DC=local
Administrator@htb.local


CN=Enterprise Admins,CN=Users,DC=htb,DC=local
Administrator@htb.local


CN=Schema Admins,CN=Users,DC=htb,DC=local
Administrator@htb.local


CN=Denied RODC Password Replication Group,CN=Users,DC=htb,DC=local
CN=Read-only Domain Controllers,CN=Users,DC=htb,DC=local
CN=Group Policy Creator Owners,CN=Users,DC=htb,DC=local
CN=Domain Admins,CN=Users,DC=htb,DC=local
CN=Cert Publishers,CN=Users,DC=htb,DC=local
CN=Enterprise Admins,CN=Users,DC=htb,DC=local
CN=Schema Admins,CN=Users,DC=htb,DC=local
CN=Domain Controllers,CN=Users,DC=htb,DC=local
CN=krbtgt,CN=Users,DC=htb,DC=local


CN=System Managed Accounts Group,CN=Builtin,DC=htb,DC=local
CN=DefaultAccount,CN=Users,DC=htb,DC=local


CN=Remote Management Users,CN=Builtin,DC=htb,DC=local
CN=Privileged IT Accounts,OU=Security Groups,DC=htb,DC=local


CN=IIS_IUSRS,CN=Builtin,DC=htb,DC=local
CN=S-1-5-17,CN=ForeignSecurityPrincipals,DC=htb,DC=local


CN=Guests,CN=Builtin,DC=htb,DC=local
CN=Domain Guests,CN=Users,DC=htb,DC=local
CN=Guest,CN=Users,DC=htb,DC=local


CN=Users,CN=Builtin,DC=htb,DC=local
CN=Domain Users,CN=Users,DC=htb,DC=local
CN=S-1-5-11,CN=ForeignSecurityPrincipals,DC=htb,DC=local
CN=S-1-5-4,CN=ForeignSecurityPrincipals,DC=htb,DC=local


CN=Administrators,CN=Builtin,DC=htb,DC=local
CN=Domain Admins,CN=Users,DC=htb,DC=local
CN=Enterprise Admins,CN=Users,DC=htb,DC=local
Administrator@htb.local


CN=Windows Authorization Access Group,CN=Builtin,DC=htb,DC=local
CN=Exchange Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=S-1-5-9,CN=ForeignSecurityPrincipals,DC=htb,DC=local


CN=Pre-Windows 2000 Compatible Access,CN=Builtin,DC=htb,DC=local
CN=S-1-1-0,CN=ForeignSecurityPrincipals,DC=htb,DC=local
CN=S-1-5-7,CN=ForeignSecurityPrincipals,DC=htb,DC=local


CN=Account Operators,CN=Builtin,DC=htb,DC=local
CN=Privileged IT Accounts,OU=Security Groups,DC=htb,DC=local


CN=Privileged IT Accounts,OU=Security Groups,DC=htb,DC=local
CN=Service Accounts,OU=Security Groups,DC=htb,DC=local


CN=Service Accounts,OU=Security Groups,DC=htb,DC=local
svc-alfresco@htb.local


CN=Exchange Install Domain Servers,CN=Microsoft Exchange System Objects,DC=htb,DC=local
CN=EXCH01,CN=Computers,DC=htb,DC=local


CN=Exchange Windows Permissions,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=Exchange Trusted Subsystem,OU=Microsoft Exchange Security Groups,DC=htb,DC=local


CN=Managed Availability Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=Exchange Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=EXCH01,CN=Computers,DC=htb,DC=local


CN=Exchange Trusted Subsystem,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=EXCH01,CN=Computers,DC=htb,DC=local


CN=Exchange Servers,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
CN=Exchange Install Domain Servers,CN=Microsoft Exchange System Objects,DC=htb,DC=local
CN=EXCH01,CN=Computers,DC=htb,DC=local


CN=Organization Management,OU=Microsoft Exchange Security Groups,DC=htb,DC=local
Administrator@htb.local


[+] Organizational Units Found [15]
OU=Domain Controllers,DC=htb,DC=local
OU=Reception,OU=Employees,DC=htb,DC=local
OU=Marketing,OU=Employees,DC=htb,DC=local
OU=Sales,OU=Employees,DC=htb,DC=local
OU=Sysadmins,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Helpdesk,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=IT Management,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Application Support,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Developers,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Exchange Administrators,OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Information Technology,OU=Employees,DC=htb,DC=local
OU=Employees,DC=htb,DC=local
OU=Security Groups,DC=htb,DC=local
OU=Service Accounts,DC=htb,DC=local
OU=Microsoft Exchange Security Groups,DC=htb,DC=local


[+] Key Strings [57]
(SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}@htb.local) msExchBypassAudit=FALSE
(SystemMailbox{2CE34405-31BE-455D-89D7-A7C7DA7A0DAA}@htb.local) msExchBypassAudit=FALSE
(SystemMailbox{D0E409A0-AF9B-4720-92FE-AAC869B0D201}@htb.local) msExchBypassAudit=FALSE
(FederatedEmail.4c1f4d8b-8179-4148-93bf-00a95fa1e042@htb.local) msExchBypassAudit=FALSE
(Migration.8f3e7716-2011-43e4-96b1-aba62d229136@htb.local) msExchBypassAudit=FALSE
(DiscoverySearchMailbox {D919BA05-46A6-415f-80AD-7E09334BB852}@htb.local) msExchBypassAudit=FALSE
(SystemMailbox{e0dc1c29-89c3-4034-b678-e6c29d823ed9}@htb.local) msExchBypassAudit=FALSE
(SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}@htb.local) msExchBypassAudit=FALSE
(SystemMailbox{1f05a927-89c0-4725-adca-4527114196a1}@htb.local) msExchBypassAudit=FALSE
(Exchange_Online-ApplicationAccount@htb.local) msExchBypassAudit=FALSE
Members of this group can perform administrative actions on key objects within the forest.
Members of this group can perform administrative actions on key objects within the domain.
CN=Denied RODC Password Replication Group,CN=Users,DC=htb,DC=local
Denied RODC Password Replication Group
Members in this group cannot have their passwords replicated to any read-only domain controllers in the domain
CN=Denied RODC Password Replication Group,CN=Users,DC=htb,DC=local
Denied RODC Password Replication Group
Denied RODC Password Replication Group
Allowed RODC Password Replication Group
Members in this group can have their passwords replicated to all read-only domain controllers in the domain
CN=Allowed RODC Password Replication Group,CN=Users,DC=htb,DC=local
Allowed RODC Password Replication Group
Allowed RODC Password Replication Group
(Exchange_Online-ApplicationAccount@htb.local) msDS-ExpirePasswordsOnSmartCardOnlyAccounts=TRUE
(svc-alfresco@htb.local) msExchBypassAudit=FALSE
(svc-alfresco@htb.local) msExchBypassAudit=FALSE
(HealthMailbox0659cc188f4c4f9f978f6c2142c4181e@htb.local) msExchBypassAudit=FALSE
(HealthMailbox7108a4e350f84b32a7a90d8e718f78cf@htb.local) msExchBypassAudit=FALSE
(HealthMailboxb01ac647a64648d2a5fa21df27058a24@htb.local) msExchBypassAudit=FALSE
(HealthMailboxfd87238e536e49e08738480d300e3772@htb.local) msExchBypassAudit=FALSE
(HealthMailbox83d6781be36b4bbf8893b03c2ee379ab@htb.local) msExchBypassAudit=FALSE
(HealthMailbox6ded67848a234577a1756e072081d01f@htb.local) msExchBypassAudit=FALSE
(HealthMailbox968e74dd3edb414cb4018376e7dd95ba@htb.local) msExchBypassAudit=FALSE
(HealthMailbox670628ec4dd64321acfdf6e67db3a2d8@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc0a90c97d4994429b15003d6a518f3f5@htb.local) msExchBypassAudit=FALSE
(HealthMailboxfc9daad117b84fe08b081886bd8a5a50@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE
CN=Reset Password-Organization Management-Delegating,CN=Role Assignments,CN=RBAC,CN=First Organization,CN=Microsoft Exchange,CN=Services,CN=Configuration,DC=htb,DC=local
(HealthMailboxc3d7722415ad41a5b19e3e00e165edbe@htb.local) msExchBypassAudit=FALSE


[+] Kerberoastable Users [0]
```
