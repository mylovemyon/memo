## -newpass 'PASSWORD'
変更したのに、旧パスワードでLDAPでログインできる！？
```sh
└─$ impacket-changepasswd -newpass '!QAZ2wsx' 'htb.local/svc-alfresco:s3rvice@10.129.95.210'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[*] Changing the password of htb.local\svc-alfresco
[*] Connecting to DCE/RPC as htb.local\svc-alfresco
[*] Password was changed successfully.


└─$ impacket-GetADComputers -ts -dc-ip 10.129.95.210 'htb.local/svc-alfresco:s3rvice' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-24 19:30:34] [*] Querying 10.129.95.210 for information about domain.
SAM AcctName     DNS Hostname                         OS Version       OS                   
---------------  -----------------------------------  ---------------  --------------------
FOREST$          FOREST.htb.local                     10.0 (14393)     Windows Server 2016 Standard 
EXCH01$          EXCH01.htb.local                     10.0 (14393)     Windows Server 2016 Standard 
```
