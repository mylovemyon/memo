## account
```sh
└─$ certipy-ad account read -user 'svc_tgs' -dc-ip '10.129.172.255' -u 'administrator' -p 'Ticketmaster1968' -ldap-scheme ldap 
Certipy v5.0.2 - by Oliver Lyak (ly4k)

[*] Reading attributes for 'SVC_TGS':
    cn                                  : SVC_TGS
    distinguishedName                   : CN=SVC_TGS,CN=Users,DC=active,DC=htb
    name                                : SVC_TGS
    objectSid                           : S-1-5-21-405608879-3187717380-1996298813-1103
    sAMAccountName                      : SVC_TGS
    userPrincipalName                   : SVC_TGS@active.htb
    userAccountControl                  : 66048
    whenCreated                         : 2018-07-18T20:14:38+00:00
    whenChanged                         : 2018-07-18T20:20:51+00:00
```
