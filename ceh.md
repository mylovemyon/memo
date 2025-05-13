# Footprinting and Reconnaissance
## Lab 1: Perform Footprinting Through Search Engines
### Task 1: Gather Information using Advanced Google Hacking Techniques
cache allinurl inurl allintitle inanchor allinanchor link related info location
### Task 2: Gather Information from Video Search Engine
- https://mattw.io/youtube-metadata/
- You can use other video search engines such as Google videos (https://www.google.com/videohp)
- Yahoo videos (https://in.video.search.yahoo.com)
- video analysis tools such as EZGif (https://ezgif.com), VideoReverser.com (https://www.videoreverser.com)
- and reverse image search tools such as TinEye Reverse Image Search (https://tineye.com)
- Yahoo Image Search (https://images.search.yahoo.com)
### Task 3: Gather Information from FTP Search Engines
https://www.searchftps.net/ 
### Task 4: Gather Information from IoT Search Engines
https://www.shodan.io/

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
`theHarvester -d microsoft.com -l 200 -b baidu`
### Task 4: Gather Information using Deep and Dark Web Searching
Tor Browser
- The Hidden Wiki is an onion site that works as a Wikipedia service of hidden websites. (http://zqktlwiuavvvqqt4ybvgvi7tyo4hjl5xgfuvpdf6otjiycgwqbym2qad.onion/wiki)
- FakeID is an onion site for creating fake passports (http://ymvhtqya23wqpez63gyc3ke4svju3mqsby2awnhd3bk2e65izt7baqad.onion)
- Cardshop is an onion site that sells cards with good balances (http://s57divisqlcjtsyutxjz2ww77vlbwpxgodtijcsrgsuts4js5hnxkhqd.onion)

You can also use tools such as ExoneraTor (https://metrics.torproject.org), OnionLand Search engine (https://onionlandsearchengine.com), etc. to perform deep and dark web browsing.
### Task 5: Determine Target OS Through Passive Footprinting
https://search.censys.io

## Lab 3: Perform Footprinting Through Social Networking Sites
### Task 1: Gather Employees' Information from LinkedIn using theHarvester
`theHarvester -d eccouncil -l 200 -b linkedin`
### Task 2: Gather Personal Information from Various Social Networking Sites using Sherlock
`sherlock "satya nadella"`
- https://www.social-searcher.com
- https://github.com/wishihab/userrecon

## Lab 4: Perform Website Footprinting
### Task 1: Gather Information About a Target Website using Ping Command Line Utility
`ping`
### Task 2: Gather Information about a Target Website using Photon
`python3 photon.py -u http://www.certifiedhacker.com`
### Task 3: Gather Information About a Target Website using Central Ops
- https://centralops.net
- https://website.informer.com
### Task 4: Extract a Company's Data using Web Data Extractor
`Web Data Extractor`
- https://www.parsehub.com
- https://www.spiderfoot.net
### Task 5: Mirror a Target Website using HTTrack Web Site Copier
`HTTrack Web Site Copier`
- https://www.cyotek.com
### Task 6: Gather Information About a Target Website using GRecon
`python3 grecon.py`
### Task 7: Gather a Wordlist from the Target Website using CeWL
`cewl -w wordlist.txt -d 2 -m 5 https://www.certifiedhacker.com`

## Lab 5: Perform Email Footprinting
### Task 1: Gather Information about a Target by Tracing Emails using eMailTrackerPro
`eMailTrackerPro`
- https://mailtrack.io
- https://github.com/robertswin/Infoga

## Lab 6: Perform Whois Footprinting
### Task 1: Perform Whois Lookup using DomainTools
- http://whois.domaintools.com
- https://www.tamos.com
- http://www.sabsoft.com

## Lab 7: Perform DNS Footprinting
### Task 1: Gather DNS Information using nslookup Command Line Utility and Online Tool
`nslookup`
- http://www.kloth.net/services/nslookup.php
- https://dnsdumpster.com
- https://network-tools.com
### Task 2: Perform Reverse DNS Lookup using Reverse IP Domain Check and DNSRecon
`./dnsrecon.py -r 162.241.216.0-162.241.216.255`
- https://www.yougetsignal.com
### Task 3: Gather Information of Subdomain and DNS Records using SecurityTrails
- https://securitytrails.com/
- https://dnschecker.org
- https://dnsdumpster.com

## Lab 8: Perform Network Footprinting
