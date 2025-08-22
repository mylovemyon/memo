```sh
└─$ ldapdomaindump -u 'htb.local\svc-alfresco' -p s3rvice -at NTLM --no-json --no-grep ldap://10.129.158.167  
[*] Connecting to host...
[*] Binding to host
[+] Bind OK
[*] Starting domain dump
[+] Domain dump finished


└─$ ls domain_*                                                                                               
domain_computers_by_os.html  domain_computers.html  domain_groups.html  domain_policy.html  domain_trusts.html  domain_users_by_group.html  domain_users.html
```
