```
└─$ impacket-owneredit -debug -dc-ip 10.129.25.235 -target 'SERVICE ACCOUNTS' -action read 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Initializing domainDumper()
[+] Target principal found in LDAP (SERVICE ACCOUNTS)
[*] Current owner information below
[*] - SID: S-1-5-21-3072663084-364016917-1341370565-512
[*] - sAMAccountName: Domain Admins
[*] - distinguishedName: CN=Domain Admins,CN=Users,DC=htb,DC=local
```
