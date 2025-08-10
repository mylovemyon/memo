## http-methods
```sh
└─$ nmap -n -Pn -p80 --script=http-methods 10.129.95.234 -d 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-08-09 04:59 EDT
--------------- Timing report ---------------
  hostgroups: min 1, max 100000
  rtt-timeouts: init 1000, min 100, max 10000
  max-scan-delay: TCP 1000, UDP 1000, SCTP 1000
  parallelism: min 0, max 0
  max-retries: 10, host-timeout: 0
  min-rate: 0, max-rate: 0
---------------------------------------------
NSE: Using Lua 5.4.
NSE: Arguments from CLI: 
NSE: Loaded 1 scripts for scanning.
NSE: Script Pre-scanning.
NSE: Starting runlevel 1 (of 1) scan.
Initiating NSE at 04:59
Completed NSE at 04:59, 0.00s elapsed
Initiating SYN Stealth Scan at 04:59
Scanning 10.129.95.234 [1 port]
Packet capture filter (device tun0): dst host 10.10.16.23 and (icmp or icmp6 or ((tcp or udp or sctp) and (src host 10.129.95.234)))
Discovered open port 80/tcp on 10.129.95.234
Completed SYN Stealth Scan at 04:59, 0.33s elapsed (1 total ports)
Overall sending rates: 3.05 packets / s, 134.07 bytes / s.
NSE: Script scanning 10.129.95.234.
NSE: Starting runlevel 1 (of 1) scan.
Initiating NSE at 04:59
NSE: Starting http-methods against 10.129.95.234:80.
NSE: [http-methods 10.129.95.234:80] HTTP Status for OPTIONS is 200
NSE: [http-methods 10.129.95.234:80] Response Code to Random Method is 501
NSE: Finished http-methods against 10.129.95.234:80.
Completed NSE at 04:59, 3.96s elapsed
Nmap scan report for 10.129.95.234
Host is up, received user-set (0.31s latency).
Scanned at 2025-08-09 04:59:07 EDT for 4s

PORT   STATE SERVICE REASON
80/tcp open  http    syn-ack ttl 127
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD DELETE COPY MOVE PROPFIND PROPPATCH SEARCH MKCOL LOCK UNLOCK PUT POST
|_  Potentially risky methods: TRACE DELETE COPY MOVE PROPFIND PROPPATCH SEARCH MKCOL LOCK UNLOCK PUT
Final times for host: srtt: 307187 rttvar: 307187  to: 1535935

NSE: Script Post-scanning.
NSE: Starting runlevel 1 (of 1) scan.
Initiating NSE at 04:59
Completed NSE at 04:59, 0.00s elapsed
Read from /usr/share/nmap: nmap-protocols nmap-services.
Nmap done: 1 IP address (1 host up) scanned in 4.38 seconds
           Raw packets sent: 1 (44B) | Rcvd: 1 (44B)
```



# tips
## TARGET SPECIFICATION
https://nmap.org/book/man-target-specification.html  
おすすめオプション
- `-n`：ターゲットIPの逆リゾルバ（デフォルトで有効）を無効にする


## HOST DISCOVERY
https://nmap.org/book/man-host-discovery.html  
おすすめオプション
- `-Pn`  
ターゲットに対するポートスキャンの前に生存確認のため、ICMP echo reequest、ポート80へのTCP ACK、ポート443へのTCP SYN、ICMP Timestamp queryの４つが送信される。これらを無効したいときに便利


## SCAN TECHNIQUES
https://nmap.org/book/man-port-scanning-basics.html  
https://nmap.org/book/man-port-scanning-techniques.html  
デフォルトでTCPポートを1000個スキャンする


## PORT SPECIFICATION AND SCAN ORDER
https://nmap.org/book/man-port-specification.html  
おすすめオプション
- `--top-ports 数値`
  よく使われるポートをN個ポートスキャン


## SERVICE/VERSION DETECTION
https://nmap.org/book/man-version-detection.html  
おすすめオプション
- `--version-all`  
  `-sV`オプションより詳細にバージョン検出できる


## SCRIPT SCAN
https://nmap.org/book/man-nse.html  
https://nmap.org/book/nse.html  
https://nmap.org/nsedoc/scripts
```
└─$ ls /usr/share/nmap/scripts 
acarsd-info.nse                       dns-random-txid.nse                 http-huawei-hg5xx-vuln.nse              ip-geolocation-map-bing.nse       ntp-info.nse                    smtp-brute.nse
address-info.nse                      dns-recursion.nse                   http-icloud-findmyiphone.nse            ip-geolocation-map-google.nse     ntp-monlist.nse                 smtp-commands.nse
afp-brute.nse                         dns-service-discovery.nse           http-icloud-sendmsg.nse                 ip-geolocation-map-kml.nse        omp2-brute.nse                  smtp-enum-users.nse
afp-ls.nse                            dns-srv-enum.nse                    http-iis-short-name-brute.nse           ip-geolocation-maxmind.nse        omp2-enum-targets.nse           smtp-ntlm-info.nse
afp-path-vuln.nse                     dns-update.nse                      http-iis-webdav-vuln.nse                ip-https-discover.nse             omron-info.nse                  smtp-open-relay.nse
afp-serverinfo.nse                    dns-zeustracker.nse                 http-internal-ip-disclosure.nse         ipidseq.nse                       openflow-info.nse               smtp-strangeport.nse
afp-showmount.nse                     dns-zone-transfer.nse               http-joomla-brute.nse                   ipmi-brute.nse                    openlookup-info.nse             smtp-vuln-cve2010-4344.nse
ajp-auth.nse                          docker-version.nse                  http-jsonp-detection.nse                ipmi-cipher-zero.nse              openvas-otp-brute.nse           smtp-vuln-cve2011-1720.nse
ajp-brute.nse                         domcon-brute.nse                    http-litespeed-sourcecode-download.nse  ipmi-version.nse                  openwebnet-discovery.nse        smtp-vuln-cve2011-1764.nse
ajp-headers.nse                       domcon-cmd.nse                      http-ls.nse                             ipv6-multicast-mld-list.nse       oracle-brute.nse                sniffer-detect.nse
ajp-methods.nse                       domino-enum-users.nse               http-majordomo2-dir-traversal.nse       ipv6-node-info.nse                oracle-brute-stealth.nse        snmp-brute.nse
ajp-request.nse                       dpap-brute.nse                      http-malware-host.nse                   ipv6-ra-flood.nse                 oracle-enum-users.nse           snmp-hh3c-logins.nse
allseeingeye-info.nse                 drda-brute.nse                      http-mcmp.nse                           irc-botnet-channels.nse           oracle-sid-brute.nse            snmp-info.nse
amqp-info.nse                         drda-info.nse                       http-methods.nse                        irc-brute.nse                     oracle-tns-version.nse          snmp-interfaces.nse
asn-query.nse                         duplicates.nse                      http-method-tamper.nse                  irc-info.nse                      ovs-agent-version.nse           snmp-ios-config.nse
auth-owners.nse                       eap-info.nse                        http-mobileversion-checker.nse          irc-sasl-brute.nse                p2p-conficker.nse               snmp-netstat.nse
auth-spoof.nse                        enip-info.nse                       http-ntlm-info.nse                      irc-unrealircd-backdoor.nse       path-mtu.nse                    snmp-processes.nse
backorifice-brute.nse                 epmd-info.nse                       http-open-proxy.nse                     iscsi-brute.nse                   pcanywhere-brute.nse            snmp-sysdescr.nse
backorifice-info.nse                  eppc-enum-processes.nse             http-open-redirect.nse                  iscsi-info.nse                    pcworx-info.nse                 snmp-win32-services.nse
bacnet-info.nse                       fcrdns.nse                          http-passwd.nse                         isns-info.nse                     pgsql-brute.nse                 snmp-win32-shares.nse
banner.nse                            finger.nse                          http-phpmyadmin-dir-traversal.nse       jdwp-exec.nse                     pjl-ready-message.nse           snmp-win32-software.nse
bitcoin-getaddr.nse                   fingerprint-strings.nse             http-phpself-xss.nse                    jdwp-info.nse                     pop3-brute.nse                  snmp-win32-users.nse
bitcoin-info.nse                      firewalk.nse                        http-php-version.nse                    jdwp-inject.nse                   pop3-capabilities.nse           socks-auth-info.nse
bitcoinrpc-info.nse                   firewall-bypass.nse                 http-proxy-brute.nse                    jdwp-version.nse                  pop3-ntlm-info.nse              socks-brute.nse
bittorrent-discovery.nse              flume-master-info.nse               http-put.nse                            knx-gateway-discover.nse          port-states.nse                 socks-open-proxy.nse
bjnp-discover.nse                     fox-info.nse                        http-qnap-nas-info.nse                  knx-gateway-info.nse              pptp-version.nse                ssh2-enum-algos.nse
broadcast-ataoe-discover.nse          freelancer-info.nse                 http-referer-checker.nse                krb5-enum-users.nse               profinet-cm-lookup.nse          ssh-auth-methods.nse
broadcast-avahi-dos.nse               ftp-anon.nse                        http-rfi-spider.nse                     ldap-brute.nse                    puppet-naivesigning.nse         ssh-brute.nse
broadcast-bjnp-discover.nse           ftp-bounce.nse                      http-robots.txt.nse                     ldap-novell-getpass.nse           qconn-exec.nse                  ssh-hostkey.nse
broadcast-db2-discover.nse            ftp-brute.nse                       http-robtex-reverse-ip.nse              ldap-rootdse.nse                  qscan.nse                       ssh-publickey-acceptance.nse
broadcast-dhcp6-discover.nse          ftp-libopie.nse                     http-robtex-shared-ns.nse               ldap-search.nse                   quake1-info.nse                 ssh-run.nse
broadcast-dhcp-discover.nse           ftp-proftpd-backdoor.nse            http-sap-netweaver-leak.nse             lexmark-config.nse                quake3-info.nse                 sshv1.nse
broadcast-dns-service-discovery.nse   ftp-syst.nse                        http-security-headers.nse               llmnr-resolve.nse                 quake3-master-getservers.nse    ssl-ccs-injection.nse
broadcast-dropbox-listener.nse        ftp-vsftpd-backdoor.nse             http-server-header.nse                  lltd-discovery.nse                rdp-enum-encryption.nse         ssl-cert-intaddr.nse
broadcast-eigrp-discovery.nse         ftp-vuln-cve2010-4221.nse           http-shellshock.nse                     lu-enum.nse                       rdp-ntlm-info.nse               ssl-cert.nse
broadcast-hid-discoveryd.nse          ganglia-info.nse                    http-sitemap-generator.nse              maxdb-info.nse                    rdp-vuln-ms12-020.nse           ssl-date.nse
broadcast-igmp-discovery.nse          giop-info.nse                       http-slowloris-check.nse                mcafee-epo-agent.nse              realvnc-auth-bypass.nse         ssl-dh-params.nse
broadcast-jenkins-discover.nse        gkrellm-info.nse                    http-slowloris.nse                      membase-brute.nse                 redis-brute.nse                 ssl-enum-ciphers.nse
broadcast-listener.nse                gopher-ls.nse                       http-sql-injection.nse                  membase-http-info.nse             redis-info.nse                  ssl-heartbleed.nse
broadcast-ms-sql-discover.nse         gpsd-info.nse                       https-redirect.nse                      memcached-info.nse                resolveall.nse                  ssl-known-key.nse
broadcast-netbios-master-browser.nse  hadoop-datanode-info.nse            http-stored-xss.nse                     metasploit-info.nse               reverse-index.nse               ssl-poodle.nse
broadcast-networker-discover.nse      hadoop-jobtracker-info.nse          http-svn-enum.nse                       metasploit-msgrpc-brute.nse       rexec-brute.nse                 sslv2-drown.nse
broadcast-novell-locate.nse           hadoop-namenode-info.nse            http-svn-info.nse                       metasploit-xmlrpc-brute.nse       rfc868-time.nse                 sslv2.nse
broadcast-ospf2-discover.nse          hadoop-secondary-namenode-info.nse  http-title.nse                          mikrotik-routeros-brute.nse       riak-http-info.nse              sstp-discover.nse
broadcast-pc-anywhere.nse             hadoop-tasktracker-info.nse         http-tplink-dir-traversal.nse           mmouse-brute.nse                  rlogin-brute.nse                stun-info.nse
broadcast-pc-duo.nse                  hartip-info.nse                     http-trace.nse                          mmouse-exec.nse                   rmi-dumpregistry.nse            stun-version.nse
broadcast-pim-discovery.nse           hbase-master-info.nse               http-traceroute.nse                     modbus-discover.nse               rmi-vuln-classloader.nse        stuxnet-detect.nse
broadcast-ping.nse                    hbase-region-info.nse               http-trane-info.nse                     mongodb-brute.nse                 rpcap-brute.nse                 supermicro-ipmi-conf.nse
broadcast-pppoe-discover.nse          hddtemp-info.nse                    http-unsafe-output-escaping.nse         mongodb-databases.nse             rpcap-info.nse                  svn-brute.nse
broadcast-rip-discover.nse            hnap-info.nse                       http-useragent-tester.nse               mongodb-info.nse                  rpc-grind.nse                   targets-asn.nse
broadcast-ripng-discover.nse          hostmap-bfk.nse                     http-userdir-enum.nse                   mqtt-subscribe.nse                rpcinfo.nse                     targets-ipv6-map4to6.nse
broadcast-sonicwall-discover.nse      hostmap-crtsh.nse                   http-vhosts.nse                         mrinfo.nse                        rsa-vuln-roca.nse               targets-ipv6-multicast-echo.nse
broadcast-sybase-asa-discover.nse     hostmap-robtex.nse                  http-virustotal.nse                     msrpc-enum.nse                    rsync-brute.nse                 targets-ipv6-multicast-invalid-dst.nse
broadcast-tellstick-discover.nse      http-adobe-coldfusion-apsa1301.nse  http-vlcstreamer-ls.nse                 ms-sql-brute.nse                  rsync-list-modules.nse          targets-ipv6-multicast-mld.nse
broadcast-upnp-info.nse               http-affiliate-id.nse               http-vmware-path-vuln.nse               ms-sql-config.nse                 rtsp-methods.nse                targets-ipv6-multicast-slaac.nse
broadcast-versant-locate.nse          http-apache-negotiation.nse         http-vuln-cve2006-3392.nse              ms-sql-dac.nse                    rtsp-url-brute.nse              targets-ipv6-wordlist.nse
broadcast-wake-on-lan.nse             http-apache-server-status.nse       http-vuln-cve2009-3960.nse              ms-sql-dump-hashes.nse            rusers.nse                      targets-sniffer.nse
broadcast-wpad-discover.nse           http-aspnet-debug.nse               http-vuln-cve2010-0738.nse              ms-sql-empty-password.nse         s7-info.nse                     targets-traceroute.nse
broadcast-wsdd-discover.nse           http-auth-finder.nse                http-vuln-cve2010-2861.nse              ms-sql-hasdbaccess.nse            samba-vuln-cve-2012-1182.nse    targets-xml.nse
broadcast-xdmcp-discover.nse          http-auth.nse                       http-vuln-cve2011-3192.nse              ms-sql-info.nse                   script.db                       teamspeak2-version.nse
cassandra-brute.nse                   http-avaya-ipoffice-users.nse       http-vuln-cve2011-3368.nse              ms-sql-ntlm-info.nse              servicetags.nse                 telnet-brute.nse
cassandra-info.nse                    http-awstatstotals-exec.nse         http-vuln-cve2012-1823.nse              ms-sql-query.nse                  shodan-api.nse                  telnet-encryption.nse
cccam-version.nse                     http-axis2-dir-traversal.nse        http-vuln-cve2013-0156.nse              ms-sql-tables.nse                 sip-brute.nse                   telnet-ntlm-info.nse
cics-enum.nse                         http-backup-finder.nse              http-vuln-cve2013-6786.nse              ms-sql-xp-cmdshell.nse            sip-call-spoof.nse              tftp-enum.nse
cics-info.nse                         http-barracuda-dir-traversal.nse    http-vuln-cve2013-7091.nse              mtrace.nse                        sip-enum-users.nse              tftp-version.nse
cics-user-brute.nse                   http-bigip-cookie.nse               http-vuln-cve2014-2126.nse              multicast-profinet-discovery.nse  sip-methods.nse                 tls-alpn.nse
cics-user-enum.nse                    http-brute.nse                      http-vuln-cve2014-2127.nse              murmur-version.nse                skypev2-version.nse             tls-nextprotoneg.nse
citrix-brute-xml.nse                  http-cakephp-version.nse            http-vuln-cve2014-2128.nse              mysql-audit.nse                   smb2-capabilities.nse           tls-ticketbleed.nse
citrix-enum-apps.nse                  http-chrono.nse                     http-vuln-cve2014-2129.nse              mysql-brute.nse                   smb2-security-mode.nse          tn3270-screen.nse
citrix-enum-apps-xml.nse              http-cisco-anyconnect.nse           http-vuln-cve2014-3704.nse              mysql-databases.nse               smb2-time.nse                   tor-consensus-checker.nse
citrix-enum-servers.nse               http-coldfusion-subzero.nse         http-vuln-cve2014-8877.nse              mysql-dump-hashes.nse             smb2-vuln-uptime.nse            traceroute-geolocation.nse
citrix-enum-servers-xml.nse           http-comments-displayer.nse         http-vuln-cve2015-1427.nse              mysql-empty-password.nse          smb-brute.nse                   tso-brute.nse
clamav-exec.nse                       http-config-backup.nse              http-vuln-cve2015-1635.nse              mysql-enum.nse                    smb-double-pulsar-backdoor.nse  tso-enum.nse
clock-skew.nse                        http-cookie-flags.nse               http-vuln-cve2017-1001000.nse           mysql-info.nse                    smb-enum-domains.nse            ubiquiti-discovery.nse
coap-resources.nse                    http-cors.nse                       http-vuln-cve2017-5638.nse              mysql-query.nse                   smb-enum-groups.nse             unittest.nse
couchdb-databases.nse                 http-cross-domain-policy.nse        http-vuln-cve2017-5689.nse              mysql-users.nse                   smb-enum-processes.nse          unusual-port.nse
couchdb-stats.nse                     http-csrf.nse                       http-vuln-cve2017-8917.nse              mysql-variables.nse               smb-enum-services.nse           upnp-info.nse
creds-summary.nse                     http-date.nse                       http-vuln-misfortune-cookie.nse         mysql-vuln-cve2012-2122.nse       smb-enum-sessions.nse           uptime-agent-info.nse
cups-info.nse                         http-default-accounts.nse           http-vuln-wnr1000-creds.nse             nat-pmp-info.nse                  smb-enum-shares.nse             url-snarf.nse
cups-queue-info.nse                   http-devframework.nse               http-waf-detect.nse                     nat-pmp-mapport.nse               smb-enum-users.nse              ventrilo-info.nse
cvs-brute.nse                         http-dlink-backdoor.nse             http-waf-fingerprint.nse                nbd-info.nse                      smb-flood.nse                   versant-info.nse
cvs-brute-repository.nse              http-dombased-xss.nse               http-webdav-scan.nse                    nbns-interfaces.nse               smb-ls.nse                      vmauthd-brute.nse
daap-get-library.nse                  http-domino-enum-passwords.nse      http-wordpress-brute.nse                nbstat.nse                        smb-mbenum.nse                  vmware-version.nse
daytime.nse                           http-drupal-enum.nse                http-wordpress-enum.nse                 ncp-enum-users.nse                smb-os-discovery.nse            vnc-brute.nse
db2-das-info.nse                      http-drupal-enum-users.nse          http-wordpress-users.nse                ncp-serverinfo.nse                smb-print-text.nse              vnc-info.nse
deluge-rpc-brute.nse                  http-enum.nse                       http-xssed.nse                          ndmp-fs-info.nse                  smb-protocols.nse               vnc-title.nse
dhcp-discover.nse                     http-errors.nse                     iax2-brute.nse                          ndmp-version.nse                  smb-psexec.nse                  voldemort-info.nse
dicom-brute.nse                       http-exif-spider.nse                iax2-version.nse                        nessus-brute.nse                  smb-security-mode.nse           vtam-enum.nse
dicom-ping.nse                        http-favicon.nse                    icap-info.nse                           nessus-xmlrpc-brute.nse           smb-server-stats.nse            vulners.nse
dict-info.nse                         http-feed.nse                       iec61850-mms.nse                        netbus-auth-bypass.nse            smb-system-info.nse             vuze-dht-info.nse
distcc-cve2004-2687.nse               http-fetch.nse                      iec-identify.nse                        netbus-brute.nse                  smb-vuln-conficker.nse          wdb-version.nse
dns-blacklist.nse                     http-fileupload-exploiter.nse       ike-version.nse                         netbus-info.nse                   smb-vuln-cve2009-3103.nse       weblogic-t3-info.nse
dns-brute.nse                         http-form-brute.nse                 imap-brute.nse                          netbus-version.nse                smb-vuln-cve-2017-7494.nse      whois-domain.nse
dns-cache-snoop.nse                   http-form-fuzzer.nse                imap-capabilities.nse                   nexpose-brute.nse                 smb-vuln-ms06-025.nse           whois-ip.nse
dns-check-zone.nse                    http-frontpage-login.nse            imap-ntlm-info.nse                      nfs-ls.nse                        smb-vuln-ms07-029.nse           wsdd-discover.nse
dns-client-subnet-scan.nse            http-generator.nse                  impress-remote-discover.nse             nfs-showmount.nse                 smb-vuln-ms08-067.nse           x11-access.nse
dns-fuzz.nse                          http-git.nse                        informix-brute.nse                      nfs-statfs.nse                    smb-vuln-ms10-054.nse           xdmcp-discover.nse
dns-ip6-arpa-scan.nse                 http-gitweb-projects-enum.nse       informix-query.nse                      nje-node-brute.nse                smb-vuln-ms10-061.nse           xmlrpc-methods.nse
dns-nsec3-enum.nse                    http-google-malware.nse             informix-tables.nse                     nje-pass-brute.nse                smb-vuln-ms17-010.nse           xmpp-brute.nse
dns-nsec-enum.nse                     http-grep.nse                       ip-forwarding.nse                       nntp-ntlm-info.nse                smb-vuln-regsvc-dos.nse         xmpp-info.nse
dns-nsid.nse                          http-headers.nse                    ip-geolocation-geoplugin.nse            nping-brute.nse                   smb-vuln-webexec.nse
dns-random-srcport.nse                http-hp-ilo-info.nse                ip-geolocation-ipinfodb.nse             nrpe-enum.nse                     smb-webexec-exploit.nse
```


## OS DETECTION
https://nmap.org/book/man-os-detection.html  
ターゲットが仮想・コンテナかされていたりすると、ホストOSを検出したりするので信頼性は低い


## TIMING AND PERFORMANCE
https://nmap.org/book/man-performance.html  
おすすめオプション
- `--max-retries 0`  
  デフォルトでは再送信は１回なので、０回にし高速化


## FIREWALL/IDS EVASION AND SPOOFING
https://nmap.org/book/man-bypass-firewalls-ids.html  
おすすめオプション
- `-e イーサネット名`  
  送信元イーサネットを指定


## OUTPUT
https://nmap.org/book/man-output.html  
おすすめオプション
- `--reason`  
  ホストまたはポートの状態を決定したタイプを表示
- `-oN 出力ファイル名`  
  実行結果を通常出力
- `--stats-every 数値`  
  指定した間隔ごとにステータスメッセージを表示


## MISC
https://nmap.org/book/man-misc-options.html
