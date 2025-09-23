```sh
└─$ impacket-rpcdump -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[*] Retrieving endpoint list from 10.129.25.235
[+] StringBinding ncacn_ip_tcp:10.129.25.235[135]
Protocol: N/A 
Provider: N/A 
UUID    : D09BDEB5-6171-4A34-BFE2-06FA82652568 v1.0 
Bindings: 
          ncalrpc:[csebpub]
          ncalrpc:[LRPC-2e45226cd558d1282a]
          ncalrpc:[LRPC-a176b372664b735982]
          ncacn_np:\\FOREST[\pipe\LSM_API_service]
          ncalrpc:[LSMApi]
          ncalrpc:[LRPC-f28828d200525eda0b]
          ncalrpc:[actkernel]
          ncalrpc:[umpo]
          ncalrpc:[LRPC-a176b372664b735982]
          ncacn_np:\\FOREST[\pipe\LSM_API_service]
          ncalrpc:[LSMApi]
          ncalrpc:[LRPC-f28828d200525eda0b]
          ncalrpc:[actkernel]
          ncalrpc:[umpo]
          ncalrpc:[LRPC-3db0ac4a23424e9a71]
          ncacn_ip_tcp:10.129.25.235[49665]
          ncacn_np:\\FOREST[\pipe\eventlog]
          ncalrpc:[eventlog]
          ncalrpc:[dhcpcsvc]
          ncalrpc:[dhcpcsvc6]
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: N/A 
Provider: N/A 
UUID    : 697DCDA9-3BA9-4EB2-9247-E11F1901B0D2 v1.0 
Bindings: 
          ncalrpc:[LRPC-2e45226cd558d1282a]
          ncalrpc:[LRPC-a176b372664b735982]
          ncacn_np:\\FOREST[\pipe\LSM_API_service]
          ncalrpc:[LSMApi]
          ncalrpc:[LRPC-f28828d200525eda0b]
          ncalrpc:[actkernel]
          ncalrpc:[umpo]

Protocol: N/A 
Provider: sysntfy.dll 
UUID    : C9AC6DB5-82B7-4E55-AE8A-E464ED7B4277 v1.0 Impl friendly name
Bindings: 
          ncalrpc:[LRPC-f28828d200525eda0b]
          ncalrpc:[actkernel]
          ncalrpc:[umpo]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]
          ncalrpc:[IUserProfile2]
          ncalrpc:[IUserProfile2]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: N/A 
Provider: winlogon.exe 
UUID    : 76F226C3-EC14-4325-8A99-6A46348418AF v1.0 
Bindings: 
          ncalrpc:[WindowsShutdown]
          ncacn_np:\\FOREST[\PIPE\InitShutdown]
          ncalrpc:[WMsgKRpc071BE0]
          ncalrpc:[WMsgKRpc072041]

Protocol: [MS-RSP]: Remote Shutdown Protocol 
Provider: wininit.exe 
UUID    : D95AFE70-A6D5-4259-822E-2C84DA1DDB0D v1.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49664]
          ncalrpc:[WindowsShutdown]
          ncacn_np:\\FOREST[\PIPE\InitShutdown]
          ncalrpc:[WMsgKRpc071BE0]

Protocol: N/A 
Provider: N/A 
UUID    : 3473DD4D-2E88-4006-9CBA-22570909DD10 v5.1 WinHttp Auto-Proxy Service
Bindings: 
          ncalrpc:[OLE9F15F6BE31819C8BAAF277548324]
          ncalrpc:[LRPC-0ddb424bac3f1be144]

Protocol: N/A 
Provider: nsisvc.dll 
UUID    : 7EA70BCF-48AF-4F6A-8968-6A440754D5FA v1.0 NSI server endpoint
Bindings: 
          ncalrpc:[LRPC-0ddb424bac3f1be144]

Protocol: N/A 
Provider: N/A 
UUID    : A500D4C6-0DD1-4543-BC0C-D5F93486EAF8 v1.0 
Bindings: 
          ncalrpc:[LRPC-60bf884b6be9be13d5]
          ncalrpc:[LRPC-3db0ac4a23424e9a71]
          ncacn_ip_tcp:10.129.25.235[49665]
          ncacn_np:\\FOREST[\pipe\eventlog]
          ncalrpc:[eventlog]
          ncalrpc:[dhcpcsvc]
          ncalrpc:[dhcpcsvc6]
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: [MS-EVEN6]: EventLog Remoting Protocol 
Provider: wevtsvc.dll 
UUID    : F6BEAFF7-1E19-4FBB-9F8F-B89E2018337C v1.0 Event log TCPIP
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49665]
          ncacn_np:\\FOREST[\pipe\eventlog]
          ncalrpc:[eventlog]
          ncalrpc:[dhcpcsvc]
          ncalrpc:[dhcpcsvc6]
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: N/A 
Provider: dhcpcsvc.dll 
UUID    : 3C4728C5-F0AB-448B-BDA1-6CE01EB0A6D5 v1.0 DHCP Client LRPC Endpoint
Bindings: 
          ncalrpc:[dhcpcsvc]
          ncalrpc:[dhcpcsvc6]
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: N/A 
Provider: dhcpcsvc6.dll 
UUID    : 3C4728C5-F0AB-448B-BDA1-6CE01EB0A6D6 v1.0 DHCPv6 Client LRPC Endpoint
Bindings: 
          ncalrpc:[dhcpcsvc6]
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: N/A 
Provider: nrpsrv.dll 
UUID    : 30ADC50C-5CBC-46CE-9A0E-91914789E23C v1.0 NRP server endpoint
Bindings: 
          ncalrpc:[LRPC-ee8fc3fd0d9fe14919]

Protocol: N/A 
Provider: N/A 
UUID    : 0D3C7F20-1C8D-4654-A1B3-51563B298BDA v1.0 UserMgrCli
Bindings: 
          ncalrpc:[LRPC-390d764c6afd57ce61]
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: N/A 
UUID    : B18FBAB6-56F8-4702-84E0-41053293A869 v1.0 UserMgrCli
Bindings: 
          ncalrpc:[LRPC-390d764c6afd57ce61]
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: N/A 
UUID    : C49A5A70-8A7F-4E70-BA16-1E8F1F193EF1 v1.0 Adh APIs
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: IKEEXT.DLL 
UUID    : A398E520-D59A-4BDD-AA7A-3C1E0303A511 v1.0 IKE/Authip API
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: N/A 
UUID    : C36BE077-E14B-4FE9-8ABC-E856EF4F048B v1.0 Proxy Manager client server endpoint
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: N/A 
UUID    : 2E6035B2-E8F1-41A7-A044-656B439C4C34 v1.0 Proxy Manager provider server endpoint
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: iphlpsvc.dll 
UUID    : 552D076A-CB29-4E44-8B6A-D15E59E2C0AF v1.0 IP Transition Configuration endpoint
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: N/A 
UUID    : 3A9EF155-691D-4449-8D05-09AD57031823 v1.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: [MS-TSCH]: Task Scheduler Service Remoting Protocol 
Provider: schedsvc.dll 
UUID    : 86D35949-83C9-4044-B424-DB363231FD0C v1.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49667]
          ncalrpc:[ubpmtaskhostchannel]
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: [MS-TSCH]: Task Scheduler Service Remoting Protocol 
Provider: taskcomp.dll 
UUID    : 378E52B0-C0A9-11CF-822D-00AA0051E40F v1.0 
Bindings: 
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: [MS-TSCH]: Task Scheduler Service Remoting Protocol 
Provider: taskcomp.dll 
UUID    : 1FF70682-0A51-30E8-076D-740BE8CEE98B v1.0 
Bindings: 
          ncacn_np:\\FOREST[\PIPE\atsvc]
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: schedsvc.dll 
UUID    : 0A74EF1C-41A4-4E06-83AE-DC74FB1CDD53 v1.0 
Bindings: 
          ncalrpc:[senssvc]
          ncalrpc:[OLEF0B25FC33B1F6A9D1623F444C650]
          ncalrpc:[IUserProfile2]

Protocol: N/A 
Provider: gpsvc.dll 
UUID    : 2EB08E3E-639F-4FBA-97B1-14F878961076 v1.0 Group Policy RPC Interface
Bindings: 
          ncalrpc:[LRPC-c937ebf950e468661c]

Protocol: N/A 
Provider: N/A 
UUID    : 7F1343FE-50A9-4927-A778-0C5859517BAC v1.0 DfsDs service
Bindings: 
          ncacn_np:\\FOREST[\PIPE\wkssvc]
          ncalrpc:[LRPC-39c2b32f7491270abc]
          ncalrpc:[DNSResolver]

Protocol: N/A 
Provider: N/A 
UUID    : EB081A0D-10EE-478A-A1DD-50995283E7A8 v3.0 Witness Client Test Interface
Bindings: 
          ncalrpc:[LRPC-39c2b32f7491270abc]
          ncalrpc:[DNSResolver]

Protocol: N/A 
Provider: N/A 
UUID    : F2C9B409-C1C9-4100-8639-D8AB1486694A v1.0 Witness Client Upcall Server
Bindings: 
          ncalrpc:[LRPC-39c2b32f7491270abc]
          ncalrpc:[DNSResolver]

Protocol: N/A 
Provider: N/A 
UUID    : DF4DF73A-C52D-4E3A-8003-8437FDF8302A v0.0 WM_WindowManagerRPC\Server
Bindings: 
          ncalrpc:[LRPC-b9418aac4a4d112614]
          ncalrpc:[OLE1DA9CDF20AEE07158302EED2AFCE]
          ncalrpc:[LRPC-e82860f7f048e113a6]
          ncalrpc:[LRPC-33782107d1261b8e67]

Protocol: N/A 
Provider: MPSSVC.dll 
UUID    : 2FB92682-6599-42DC-AE13-BD2CA89BD11C v1.0 Fw APIs
Bindings: 
          ncalrpc:[LRPC-e82860f7f048e113a6]
          ncalrpc:[LRPC-33782107d1261b8e67]

Protocol: N/A 
Provider: N/A 
UUID    : F47433C3-3E9D-4157-AAD4-83AA1F5C2D4C v1.0 Fw APIs
Bindings: 
          ncalrpc:[LRPC-e82860f7f048e113a6]
          ncalrpc:[LRPC-33782107d1261b8e67]

Protocol: N/A 
Provider: MPSSVC.dll 
UUID    : 7F9D11BF-7FB9-436B-A812-B2D50C5D4C03 v1.0 Fw APIs
Bindings: 
          ncalrpc:[LRPC-e82860f7f048e113a6]
          ncalrpc:[LRPC-33782107d1261b8e67]

Protocol: N/A 
Provider: BFE.DLL 
UUID    : DD490425-5325-4565-B774-7E27D6C09C24 v1.0 Base Firewall Engine API
Bindings: 
          ncalrpc:[LRPC-33782107d1261b8e67]

Protocol: [MS-FASP]: Firewall and Advanced Security Protocol 
Provider: FwRemoteSvr.dll 
UUID    : 6B5BDD1E-528C-422C-AF8C-A4079BE4FE48 v1.0 Remote Fw APIs
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49670]
          ncalrpc:[ipsec]

Protocol: N/A 
Provider: efssvc.dll 
UUID    : 04EEB297-CBF4-466B-8A2A-BFD6A2F10BBA v1.0 EFSK RPC Interface
Bindings: 
          ncacn_np:\\FOREST[\pipe\efsrpc]
          ncalrpc:[LRPC-6557c71eef03a588bc]

Protocol: N/A 
Provider: efssvc.dll 
UUID    : DF1941C5-FE89-4E79-BF10-463657ACF44D v1.0 EFS RPC Interface
Bindings: 
          ncacn_np:\\FOREST[\pipe\efsrpc]
          ncalrpc:[LRPC-6557c71eef03a588bc]

Protocol: [MS-NRPC]: Netlogon Remote Protocol 
Provider: netlogon.dll 
UUID    : 12345678-1234-ABCD-EF00-01234567CFFB v1.0 
Bindings: 
          ncalrpc:[NETLOGON_LRPC]
          ncacn_ip_tcp:10.129.25.235[49675]
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: [MS-RAA]: Remote Authorization API Protocol 
Provider: N/A 
UUID    : 0B1C2170-5732-4E0E-8CD3-D9B16F3B84D7 v0.0 RemoteAccessCheck
Bindings: 
          ncalrpc:[NETLOGON_LRPC]
          ncacn_ip_tcp:10.129.25.235[49675]
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]
          ncalrpc:[NETLOGON_LRPC]
          ncacn_ip_tcp:10.129.25.235[49675]
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: [MS-SAMR]: Security Account Manager (SAM) Remote Protocol 
Provider: samsrv.dll 
UUID    : 12345778-1234-ABCD-EF00-0123456789AC v1.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49675]
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: [MS-LSAT]: Local Security Authority (Translation Methods) Remote 
Provider: lsasrv.dll 
UUID    : 12345778-1234-ABCD-EF00-0123456789AB v0.0 
Bindings: 
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: [MS-NSPI]: Name Service Provider Interface (NSPI) Protocol 
Provider: ntdsai.dll 
UUID    : F5CC5A18-4264-101A-8C59-08002B2F8426 v56.0 MS NT Directory NSP Interface
Bindings: 
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: [MS-DRSR]: Directory Replication Service (DRS) Remote Protocol 
Provider: ntdsai.dll 
UUID    : E3514235-4B06-11D1-AB04-00C04FC2DCD2 v4.0 MS NT Directory DRS Interface
Bindings: 
          ncacn_np:\\FOREST[\pipe\161180be54676318]
          ncacn_http:10.129.25.235[49674]
          ncalrpc:[NTDS_LPC]
          ncalrpc:[OLE46814DB1681B80255F40EA32E17D]
          ncacn_ip_tcp:10.129.25.235[49666]
          ncalrpc:[samss lpc]
          ncalrpc:[SidKey Local End Point]
          ncalrpc:[protected_storage]
          ncalrpc:[lsasspirpc]
          ncalrpc:[lsapolicylookup]
          ncalrpc:[LSA_EAS_ENDPOINT]
          ncalrpc:[lsacap]
          ncalrpc:[LSARPC_ENDPOINT]
          ncalrpc:[securityevent]
          ncalrpc:[audit]
          ncacn_np:\\FOREST[\pipe\lsass]

Protocol: N/A 
Provider: N/A 
UUID    : 1A0D010F-1C33-432C-B0F5-8CF4E8053099 v1.0 IdSegSrv service
Bindings: 
          ncalrpc:[LRPC-b58505a53cd2e8fa9b]

Protocol: N/A 
Provider: srvsvc.dll 
UUID    : 98716D03-89AC-44C7-BB8C-285824E51C4A v1.0 XactSrv service
Bindings: 
          ncalrpc:[LRPC-b58505a53cd2e8fa9b]

Protocol: N/A 
Provider: N/A 
UUID    : E38F5360-8572-473E-B696-1B46873BEEAB v1.0 
Bindings: 
          ncalrpc:[LRPC-be912a6199ead0500e]

Protocol: N/A 
Provider: N/A 
UUID    : 4C9DBF19-D39E-4BB9-90EE-8F7179B20283 v1.0 
Bindings: 
          ncalrpc:[LRPC-be912a6199ead0500e]

Protocol: [MS-CMPO]: MSDTC Connection Manager: 
Provider: msdtcprx.dll 
UUID    : 906B0CE0-C70B-1067-B317-00DD010662DA v1.0 
Bindings: 
          ncalrpc:[LRPC-af1c1c403779ce8ecc]
          ncalrpc:[OLE42783276C7B704352BD9C39639DE]
          ncalrpc:[LRPC-a0184abaf31b1a879c]
          ncalrpc:[LRPC-a0184abaf31b1a879c]
          ncalrpc:[LRPC-a0184abaf31b1a879c]

Protocol: [MS-SCMR]: Service Control Manager Remote Protocol 
Provider: services.exe 
UUID    : 367ABB81-9844-35F1-AD32-98F038001003 v2.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49680]

Protocol: N/A 
Provider: N/A 
UUID    : F3F09FFD-FBCF-4291-944D-70AD6E0E73BB v1.0 
Bindings: 
          ncalrpc:[LRPC-a6a5c7a32f2bb472c3]

Protocol: [MS-DNSP]: Domain Name Service (DNS) Server Management 
Provider: dns.exe 
UUID    : 50ABC2A4-574D-40B3-9D66-EE4FD5FBA076 v5.0 
Bindings: 
          ncacn_ip_tcp:10.129.25.235[49696]

Protocol: [MS-FRS2]: Distributed File System Replication Protocol 
Provider: dfsrmig.exe 
UUID    : 897E2E5F-93F3-4376-9C9C-FD2277495C27 v1.0 Frs2 Service
Bindings: 
          ncacn_ip_tcp:10.129.25.235[64184]
          ncalrpc:[OLE92E123666F9724CFF67F767137A1]

[*] Received 305 endpoints.

```
