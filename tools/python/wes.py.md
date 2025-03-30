https://github.com/bitsadmin/wesng
## Usage
```
usage: wes.py [-u] [--definitions [DEFINITIONS]] [-p INSTALLEDPATCH [INSTALLEDPATCH ...]] [-d] [-e] [--hide HIDDENVULN [HIDDENVULN ...]] [-i IMPACTS [IMPACTS ...]] [-s SEVERITIES [SEVERITIES ...]] [-o [OUTPUTFILE]] [--muc-lookup]
              [--os [OPERATING_SYSTEM]] [-c] [-h] [--update-wes]

Windows Exploit Suggester 1.05 ( https://github.com/bitsadmin/wesng/ )

options:
  -u, --update          Download latest list of CVEs
  --definitions [DEFINITIONS]
                        Definitions zip file (default: definitions.zip)
  -p, --patches INSTALLEDPATCH [INSTALLEDPATCH ...]
                        Manually specify installed patches in addition to the ones listed in the systeminfo.txt file
  -d, --usekbdate       Filter out vulnerabilities of KBs published before the publishing date of the most recent KB installed
  -e, --exploits-only   Show only vulnerabilities with known exploits
  --hide HIDDENVULN [HIDDENVULN ...]
                        Hide vulnerabilities of for example Adobe Flash Player and Microsoft Edge
  -i, --impact IMPACTS [IMPACTS ...]
                        Only display vulnerabilities with a given impact
  -s, --severity SEVERITIES [SEVERITIES ...]
                        Only display vulnerabilities with a given severity
  -o, --output [OUTPUTFILE]
                        Store results in a file
  --muc-lookup          Hide vulnerabilities if installed hotfixes are listed in the Microsoft Update Catalog as superseding hotfixes for the original BulletinKB
  --os [OPERATING_SYSTEM]
                        Specify operating system or ID from list when running without this parameter
  -c, --color           Show console output in color (requires termcolor library)
  -h, --help            Show this help message and exit
  --update-wes          Download latest version of wes.py

Examples:
  Download latest definitions
  wes.py --update
  wes.py -u

  Determine vulnerabilities
  wes.py systeminfo.txt
  
  Determine vulnerabilities using the qfe file. List the OS by first running the command without the --os parameter
  wes.py --qfe qfe.txt --os 'Windows 10 Version 20H2 for x64-based Systems'
  wes.py -q qfe.txt --os 9

  Determine vulnerabilities and output to file
  wes.py systeminfo.txt --output vulns.csv
  wes.py systeminfo.txt -o vulns.csv

  Determine vulnerabilities explicitly specifying KBs to reduce false-positives
  wes.py systeminfo.txt --patches KB4345421 KB4487017
  wes.py systeminfo.txt -p KB4345421 KB4487017
  
  Determine vulnerabilies filtering out out vulnerabilities of KBs that have been published before the publishing date of the most recent KB installed
  wes.py systeminfo.txt --usekbdate
  wes.py systeminfo.txt -d

  Determine vulnerabilities explicitly specifying definitions file
  wes.py systeminfo.txt --definitions C:\tmp\mydefs.zip

  List only vulnerabilities with exploits, excluding IE, Edge and Flash
  wes.py systeminfo.txt --exploits-only --hide "Internet Explorer" Edge Flash
  wes.py systeminfo.txt -e --hide "Internet Explorer" Edge Flash

  Only show vulnerabilities of a certain impact
  wes.py systeminfo.txt --impact "Remote Code Execution"
  wes.py systeminfo.txt -i "Remote Code Execution"
  
  Only show vulnerabilities of a certain severity
  wes.py systeminfo.txt --severity critical
  wes.py systeminfo.txt -s critical
  
  Show vulnerabilities based on missing patches 
  wes.py --missing missing.txt
  wes.py -m missing.txt
  
  Show vulnerabilities based on missing patches specifying OS
  wes.py --missing missing.txt --os "Windows 10 Version 1809 for x64-based Systems"
  wes.py -m missing.txt --os 2

  Validate supersedence against Microsoft's online Update Catalog
  wes.py systeminfo.txt --muc-lookup

  Show colored output 
  wes.py systeminfo.txt --color
  wes.py systeminfo.txt -c

  Download latest version of WES-NG
  wes.py --update-wes
```
