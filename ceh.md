# Module 02: Footprinting and Reconnaissance
## Lab 1: Perform Footprinting Through Search Engines
### Task 1: Gather Information using Advanced Google Hacking Techniques
- cache / allinurl /  inurl / allintitle / inanchor / allinanchor / link / related / info / location
### Task 2: Gather Information from Video Search Engine
- https://mattw.io/youtube-metadata/
- You can use other video search engines such as Google videos (https://www.google.com/videohp)
- Yahoo videos (https://in.video.search.yahoo.com)
- video analysis tools such as EZGif (https://ezgif.com), VideoReverser.com (https://www.videoreverser.com)
- and reverse image search tools such as TinEye Reverse Image Search (https://tineye.com)
- Yahoo Image Search (https://images.search.yahoo.com)
### Task 3: Gather Information from FTP Search Engines
- https://www.searchftps.net/ 
### Task 4: Gather Information from IoT Search Engines
- https://www.shodan.io/

## Lab 2: Perform Footprinting Through Web Services
### Task 1: Find the Company's Domains and Sub-domains using Netcraft
- https://www.netcraft.com
- https://pentest-tools.com
### Task 2: Gather Personal Information using PeekYou Online People Search Service
- https://www.peekyou.com
- https://www.spokeo.com
- https://pipl.com
- https://www.intelius.com
- https://www.beenverified.com
### Task 3: Gather an Email List using theHarvester
- `theHarvester -d microsoft.com -l 200 -b baidu`
### Task 4: Gather Information using Deep and Dark Web Searching
Tor Browser
- The Hidden Wiki is an onion site that works as a Wikipedia service of hidden websites. (http://zqktlwiuavvvqqt4ybvgvi7tyo4hjl5xgfuvpdf6otjiycgwqbym2qad.onion/wiki)
- FakeID is an onion site for creating fake passports (http://ymvhtqya23wqpez63gyc3ke4svju3mqsby2awnhd3bk2e65izt7baqad.onion)
- Cardshop is an onion site that sells cards with good balances (http://s57divisqlcjtsyutxjz2ww77vlbwpxgodtijcsrgsuts4js5hnxkhqd.onion)

You can also use tools such as ExoneraTor (https://metrics.torproject.org), OnionLand Search engine (https://onionlandsearchengine.com), etc. to perform deep and dark web browsing.
### Task 5: Determine Target OS Through Passive Footprinting
- https://search.censys.io

## Lab 3: Perform Footprinting Through Social Networking Sites
### Task 1: Gather Employees' Information from LinkedIn using theHarvester
- `theHarvester -d eccouncil -l 200 -b linkedin`
### Task 2: Gather Personal Information from Various Social Networking Sites using Sherlock
- `sherlock "satya nadella"`
- https://www.social-searcher.com
- https://github.com/wishihab/userrecon

## Lab 4: Perform Website Footprinting
### Task 1: Gather Information About a Target Website using Ping Command Line Utility
- `ping`
### Task 2: Gather Information about a Target Website using Photon
- `python3 photon.py -u http://www.certifiedhacker.com`
### Task 3: Gather Information About a Target Website using Central Ops
- https://centralops.net
- https://website.informer.com
### Task 4: Extract a Company's Data using Web Data Extractor
- `Web Data Extractor`
- https://www.parsehub.com
- https://www.spiderfoot.net
### Task 5: Mirror a Target Website using HTTrack Web Site Copier
- `HTTrack Web Site Copier`
- https://www.cyotek.com
### Task 6: Gather Information About a Target Website using GRecon
- `python3 grecon.py`
### Task 7: Gather a Wordlist from the Target Website using CeWL
- `cewl -w wordlist.txt -d 2 -m 5 https://www.certifiedhacker.com`

## Lab 5: Perform Email Footprinting
### Task 1: Gather Information about a Target by Tracing Emails using eMailTrackerPro
- `eMailTrackerPro`
- https://mailtrack.io
- https://github.com/robertswin/Infoga

## Lab 6: Perform Whois Footprinting
### Task 1: Perform Whois Lookup using DomainTools
- http://whois.domaintools.com
- https://www.tamos.com
- http://www.sabsoft.com

## Lab 7: Perform DNS Footprinting
### Task 1: Gather DNS Information using nslookup Command Line Utility and Online Tool
- `nslookup`
- http://www.kloth.net/services/nslookup.php
- https://dnsdumpster.com
- https://network-tools.com
### Task 2: Perform Reverse DNS Lookup using Reverse IP Domain Check and DNSRecon
- `./dnsrecon.py -r 162.241.216.0-162.241.216.255`
- https://www.yougetsignal.com
### Task 3: Gather Information of Subdomain and DNS Records using SecurityTrails
- https://securitytrails.com/
- https://dnschecker.org
- https://dnsdumpster.com

## Lab 8: Perform Network Footprinting
### Task 1: Locate the Network Range
- https://www.arin.net/about/welcome/region
### Task 2: Perform Network Tracerouting in Windows and Linux Machines
- `traceroute`
- http://www.visualroute.com
- https://www.solarwinds.com

## Lab 9: Perform Footprinting using Various Footprinting Tools
### Task 1: Footprinting a Target using Recon-ng
- `recon-ng`(`recon/domains-hosts/brute_hosts`,`recon/hosts-hosts/reverse_resolve`,`recon/domains-contacts/whois_pocs`,`recon/domains-hosts/hackertarget`,`reporting/html`)
### Task 2: Footprinting a Target using Maltego
- `Maltego`
### Task 3: Footprinting a Target using OSRFramework
- `OSRFramework`(`domainfy`,`searchfy`)
### Task 4: Footprinting a Target using FOCA
- `FOCA`
### Task 5: Footprinting a Target using BillCipher
- `python3 billcipher.py`
### Task 6: Footprinting a Target using OSINT Framework
- https://osintframework.com/
- https://github.com/s0md3v/ReconDog
- https://github.com/Moham3dRiahi/Th3inspector
- https://github.com/evyatarmeged/Raccoon



# Module 03: Scanning Networks
## Lab 1: Perform Host Discovery
### Task 1: Perform Host Discovery using Nmap
- `nmap -sn -PR [Target IP Address]`
- `nmap -sn -PU [Target IP Address]`
- `nmap -sn -PE [Target IP Address]`
- `nmap -sn -PP [Target IP Address]`
- `nmap -sn -PM [target IP address]`
- `nmap -sn -PS [target IP address]`
- `nmap -sn -PA [target IP address]`
- `nmap -sn -PO [target IP address]`
### Task 2: Perform Host Discovery using Angry IP Scanner
- `Angry IP Scanner`
- [SolarWinds Engineer's Toolset](https://www.solarwinds.com)
- [NetScanTools Pro](https://www.netscantools.com)
- [Colasoft Ping Tool](https://www.colasoft.com)
- [Visual Ping Tester](http://www.pingtester.net)
- [OpUtils](https://www.manageengine.com)

## Lab 2: Perform Port and Service Discovery
### Task 1: Perform Port and Service Discovery using MegaPing
- `MegaPing`
### Task 2: Perform Port and Service Discovery using NetScanTools Pro
- `NetScanTools Pro`
### Task 3: Perform Port Scanning using sx Tool
- `sx arp [Target subnet] --json | tee arp.cache`
- `cat arp.cache | sx tcp -p 1-65535 [Target IP address]`
- `cat arp.cache | sx udp --json -p [Target Port] 10.10.1.11`
### Task 4: Explore Various Network Scanning Techniques using Nmap
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
### Task 5: Explore Various Network Scanning Techniques using Hping3
- `hping3 -A [Target IP Address] -p 80 -c 5`
- `hping3 -8 0-100 -S [Target IP Address] -V`
- `hping3 -F -P -U [Target IP Address] -p 80 -c 5`
- `hping3 --scan 0-100 -S [Target IP Address]`
- `hping3 -1 [Target IP Address] -p 80 -c 5`
- `hping3 -2 [Target IP Address] -p 80 -c 5`  

## Lab 3: Perform OS Discovery
### Task 1: Identify the Target System's OS with Time-to-Live (TTL) and TCP Window Sizes using Wireshark
| Operating System | Time To Live | TCP Windows Size |
-|-|-
| linux         | 64  | 5840 |
| FreeBSD       | 64  | 65535 |
| OpenBSD       | 255 | 16384 |
| Windows       | 128 | 65535 bytes to 1 Gigabyte |
| Cisco Routers | 255 | 4128 |
| Solaris       | 255 | 8760 |
| AIX           | 255 | 16384 |
### Task 2: Perform OS Discovery using Nmap Script Engine (NSE)
- `nmap -A [Target IP Address]`
- `nmap -O  [Target IP Address]`
- `nmap --script smb-os-discovery.nse [Target IP Address]`
### Task 3: Perform OS Discovery using Unicornscan
- `unicornscan [Target IP Address] -Iv`

## Lab 4: Scan beyond IDS and Firewall
### Task 1: Scan beyond IDS/Firewall using various Evasion Techniques
- `nmap -f [Target IP Address]`
- `nmap -g 80 [Target IP Address]`
- `nmap -mtu 8 [Target IP Address]`
- `nmap -D RND:10 [Target IP Address]`
- `nmap -sT -Pn --spoof-mac 0 [Target IP Address]`
### Task 2: Create Custom Packets using Colasoft Packet Builder to Scan beyond the IDS/Firewall
- `Colasoft Packet Builder`
### Task 3: Create Custom UDP and TCP Packets using Hping3 to Scan beyond the IDS/Firewall
- `hping3 [Target IP Address] --udp --rand-source --data 500`
- `hping3 -S [Target IP Address] -p 80 -c 5`
- `hping3 [Target IP Address] --flood`  
- [NetScanTools Pro](https://www.netscantools.com)
- [Colasoft packet builder](https://www.colasoft.com)

## Lab 5: Perform Network Scanning using Various Scanning Tools
### Task 1: Scan a Target Network using Metasploit
- `auxiliary/scanner/portscan/syn`
- `auxiliary/scanner/portscan/tcp`
- `auxiliary/scanner/smb/smb_version`



# Module 04: Enumeration
## Lab 1: Perform NetBIOS Enumeration
### Task 1: Perform NetBIOS Enumeration using Windows Command-Line Utilities
- `nbtstat -a`
- `nbtstat -c`
### Task 2: Perform NetBIOS Enumeration using NetBIOS Enumerator
- `NetBIOS Enumerator`
### Task 3: Perform NetBIOS Enumeration using an NSE Script
- `nmap -sV --script nbstat.nse  [Target IP Address]`
- [Global Network Inventory](http://www.magnetosoft.com)
- [Advanced IP Scanner](https://www.advanced-ip-scanner.com)
- [Hyena](https://www.systemtools.com)
- [Nsauditor Network Security Auditor(](https://www.nsauditor.com)

## Lab 2: Perform SNMP Enumeration
### Task 1: Perform SNMP Enumeration using snmp-check
- `snmp-check [Target IP Address]`
### Task 2: Perform SNMP Enumeration using SoftPerfect Network Scanner
- `SoftPerfect Network Scanner`
- [Network Performance Monitor](https://www.solarwinds.com)
- [OpUtils](https://www.manageengine.com)
- [PRTG Network Monitor](https://www.paessler.com)
- [Engineer's Toolset](https://www.solarwinds.com)
### Task 3: Perform SNMP Enumeration using SnmpWalk
- `snmpwalk -v1 -c public [target IP]`
- `snmpwalk -v2c -c public [Target IP Address]`
### Task 4: Perform SNMP Enumeration using Nmap
- `nmap -sU -p 161 --script=snmp-sysdescr [target IP Address]`
- `nmap -sU -p 161 --script=snmp-processes [target IP Address]`
- `nmap -sU -p 161 --script=snmp-win32-software [target IP Address]`
- `nmap -sU -p 161 --script=snmp-interfaces [target IP Address]`

## Lab 3: Perform LDAP Enumeration
### Task 1: Perform LDAP Enumeration using Active Directory Explorer (AD Explorer)
- `Active Directory Explorer`
- [Softerra LDAP Administrator](https://www.ldapadministrator.com)
- [LDAP Admin Tool](https://www.ldapsoft.com)
- [LDAP Account Manager](https://www.ldap-account-manager.org)
- [LDAP Search](https://securityxploded.com)
### Task 2: Perform LDAP Enumeration using Python and Nmap
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
### Task 3: Perform LDAP Enumeration using ldapsearch
- `ldapsearch -h [Target IP Address] -x -s base namingcontexts`
- `ldapsearch -h [Target IP Address] -x -b "DC=CEH,DC=com"`
- `ldapsearch -x -h [Target IP Address] -b "DC=CEH,DC=com" "objectclass=*"`

## Lab 4: Perform NFS Enumeration
### Task 1: Perform NFS Enumeration using RPCScan and SuperEnum
- `./superenum`
- `python3 rpc-scan.py [Target IP address] --rpc`

## Lab 5: Perform DNS Enumeration
### Task 1: Perform DNS Enumeration using Zone Transfer
- `dig ns [Target Domain]`
- `dig @[[NameServer]] [[Target Domain]] axfr`
- ```cmd
  nslookup
  set querytype=soa
  [Target Domain]`
  ls -d [Name Server]
  ```
### Task 2: Perform DNS Enumeration using DNSSEC Zone Walking
- `./dnsrecon.py -d [Target domain] -z`
- [LDNS](https://www.nlnetlabs.nl)
- [nsec3map](https://github.com/anonion0/nsec3map)
- [nsec3walker](https://dnscurve.org)
- [DNSwalk](https://github.com/davebarr/dnswalk)
### Task 3: Perform DNS Enumeration using Nmap
- `nmap --script=broadcast-dns-service-discovery [Target Domain]`
- `nmap -T4 -p 53 --script dns-brute [Target Domain]`
- `nmap --script dns-srv-enum --script-args "dns-srv-enum.domain='[Target Domain]'"`

## Lab 6: Perform SMTP Enumeration
### Task 1: Perform SMTP Enumeration using Nmap
- `nmap -p 25 --script=smtp-enum-users [Target IP Address]`
- `nmap -p 25 --script=smtp-open-relay [Target IP Address]`
- `nmap -p 25 --script=smtp-commands [Target IP Address]`

## Lab 7: Perform RPC, SMB, and FTP Enumeration
### Task 1: Perform SMB and RPC Enumeration using NetScanTools Pro
- `NetScanTools Pro`
### Task 2: Perform RPC, SMB, and FTP Enumeration using Nmap
- `nmap -T4 -A [Target IP Address]`

## Lab 8: Perform Enumeration using Various Enumeration Tools
### Task 1: Enumerate Information using Global Network Inventory
- `Global Network Inventory`
### Task 2: Enumerate Network Resources using Advanced IP Scanner
- `Advanced IP Scanner`
### Task 3: Enumerate Information from Windows and Samba Hosts using Enum4linux
- `enum4linux -u martin -p apple -n [Target IP Address]`
- `enum4linux -u martin -p apple -U [Target IP Address]`
- `enum4linux -u martin -p apple -o [Target IP Address]`
- `enum4linux -u martin -p apple -P [Target IP Address]`
- `enum4linux -u martin -p apple -G [Target IP Address]`
- `enum4linux -u martin -p apple -S [Target IP Address]`
