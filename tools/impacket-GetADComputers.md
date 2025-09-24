```sh
└─$ impacket-GetADComputers -ts -debug -dc-ip 10.129.164.53 'htb.local/svc-alfresco:s3rvice' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-24 08:30:29] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-24 08:30:29] [+] Connecting to 10.129.164.53, port 389, SSL False
[2025-09-24 08:30:30] [*] Querying 10.129.164.53 for information about domain.
SAM AcctName     DNS Hostname                         OS Version       OS                   
---------------  -----------------------------------  ---------------  --------------------
[2025-09-24 08:30:30] [+] Search Filter=(&(objectCategory=computer)(objectClass=computer))
FOREST$          FOREST.htb.local                     10.0 (14393)     Windows Server 2016 Standard 
EXCH01$          EXCH01.htb.local                     10.0 (14393)     Windows Server 2016 Standard 
```
