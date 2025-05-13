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
nmap
- `-PR` : ARP ping scan
- `-PU` : UDP ping scan
- `-PE` : ICMP ECHO ping scan
- `-PP` : ICMP timestamp ping scan
- `-PM` : ICMP Address Mask Ping Scan
- `-PS` : TCP SYN Ping Scan
- `-PA` : TCP ACK Ping Scan
- `-PO` : P Protocol Ping Scan
### Task 2: Perform Host Discovery using Angry IP Scanner
- `Angry IP Scanner`
- https://www.solarwinds.com
- https://www.netscantools.com
- https://www.colasoft.com
- http://www.pingtester.net
- https://www.manageengine.com

## Lab 2: Perform Port and Service Discovery
### Task 1: Perform Port and Service Discovery using MegaPing
- `MegaPing`
### Task 2: Perform Port and Service Discovery using NetScanTools Pro
- `NetScanTools Pro`
### Task 3: Perform Port Scanning using sx Tool
- `sx arp`
- `sx tcp`
- `sx udp`
### Task 4: Explore Various Network Scanning Techniques using Nmap
nmap
- `-sT` : TCP connect/full open scan
- `-sS` : stealth scan/TCP half-open scan
- `-sX` : Xmas scan
- `-sM` : TCP Maimon scan
- `-sA` : ACK flag probe scan
- `-sN` : Null scan
- `-sl` : IDLE/IPID Header Scan
- `-sY` : SCTP INIT Scan
- `-sZ` : SCTP COOKIE ECHO Scan
- `-A` : Enable all advanced/aggressive options
### Task 5: Explore Various Network Scanning Techniques using Hping3
- `hping3 -A [Target IP Address] -p 80 -c 5`  
  -A : ACK flag
- `hping3 -8 0-100 -S [Target IP Address] -V`  
  -8 : scan mode
- `hping3 -F -P -U [Target IP Address] -p 80 -c 5`
  -F : FIN flag / -P : PUSH flag / -U : URG flag
- `hping3 --scan 0-100 -S [Target IP Address]`  
  -S:  SYN flag
- `hping3 -1 [Target IP Address] -p 80 -c 5`  
  -1 : ICMP ping scan
- `hping3 -2 [Target IP Address] -p 80 -c 5`  
  -2 : UDP scan

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
- `nmap -A`
- `nmap -O`
- `nmap --script smb-os-discovery.nse`
### Task 3: Perform OS Discovery using Unicornscan
- `unicornscan [Target IP Address] -Iv`

## Lab 4: Scan beyond IDS and Firewall
### Task 1: Scan beyond IDS/Firewall using various Evasion Techniques
nmap
- `-f` : Packet Fragmentation
- `-g` or `--source-port` : Source Port Manipulation
- `-mtu` : specifies MTU
- `-D RND:` : IP address decoy
- `--spoof-mac 0` : MAC address spoofing
### Task 2: Create Custom Packets using Colasoft Packet Builder to Scan beyond the IDS/Firewall
- `Colasoft Packet Builder`
### Task 3: Create Custom UDP and TCP Packets using Hping3 to Scan beyond the IDS/Firewall
- `hping3 [Target IP Address] --udp --rand-source --data 500`
- `hping3 [Target IP Address] --flood`  
  --flood : performs the TCP flooding

## Lab 5: Perform Network Scanning using Various Scanning Tools
### Task 1: Scan a Target Network using Metasploit
- `auxiliary/scanner/portscan/syn`
- `auxiliary/scanner/portscan/tcp`
- `auxiliary/scanner/smb/smb_version`
