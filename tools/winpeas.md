## domain

## systeminfo
```sh
*Evil-WinRM* PS C:\Users\Administrator\Documents> .\winPEASx64.exe quiet systeminfo
 [!] If you want to run the file analysis checks (search sensitive information in files), you need to specify the 'fileanalysis' or 'all' argument. Note that this search might take several minutes. For help, run winpeass.exe --help
ANSI color bit for Windows is not set. If you are executing this from a Windows terminal inside the host you should run 'REG ADD HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
Long paths are disabled, so the maximum length of a path supported is 260 chars (this may cause false negatives when looking for files). If you are admin, you can enable it with 'REG ADD HKLM\SYSTEM\CurrentControlSet\Control\FileSystem /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
  WinPEAS-ng by @hacktricks_live

       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/                                                                                                                                                  
                                                                                                                                                                                                                                            
  [+] Legend:
         Red                Indicates a special privilege over an object or something is misconfigured
         Green              Indicates that some protection is enabled or something is well configured
         Cyan               Indicates active users
         Blue               Indicates disabled users
         LightYellow        Indicates links

 You can find a Windows local PE Checklist here: https://book.hacktricks.wiki/en/windows-hardening/checklist-windows-privilege-escalation.html
   Creating Dynamic lists, this could take a while, please wait...                                                                                                                                                                          
   - Loading sensitive_files yaml definitions file...
   - Loading regexes yaml definitions file...
   - Checking if domain...
   - Getting Win32_UserAccount info...
   - Creating current user groups list...
   - Creating active users list (local only)...
   - Creating disabled users list...
   - Admin users list...
   - Creating AppLocker bypass list...
   - Creating files/directories list for search...
        [skipped, file search is disabled]


ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹ System Information ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ

ÉÍÍÍÍÍÍÍÍÍÍ¹ Basic System Information
È Check if the Windows versions is vulnerable to some known exploit https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#version-exploits
    OS Name: Microsoft Windows Server 2019 Datacenter
    OS Version: 10.0.17763 N/A Build 17763
    System Type: x64-based PC
    Hostname: SAUNA
    Domain Name: EGOTISTICAL-BANK.LOCAL
    ProductName: Windows Server 2019 Datacenter
    EditionID: ServerDatacenter
    ReleaseId: 1809
    BuildBranch: rs5_release
    CurrentMajorVersionNumber: 10
    CurrentVersion: 6.3
    Architecture: AMD64
    ProcessorCount: 2
    SystemLang: en-US
    KeyboardLang: English (United States)
    TimeZone: (UTC-08:00) Pacific Time (US & Canada)
    IsVirtualMachine: True
    Current Time: 8/9/2025 7:34:09 AM
    HighIntegrity: True
    PartOfDomain: True
    Hotfixes: KB4532947 (1/23/2020), KB4516115 (1/23/2020), KB4523204 (1/23/2020), KB4534273 (1/23/2020), 


ÉÍÍÍÍÍÍÍÍÍÍ¹ Showing All Microsoft Updates
   HotFix ID                :   KB5004228
   Installed At (UTC)       :   7/26/2021 11:17:26 PM
   Title                    :   2021-07 Cumulative Update for .NET Framework 3.5, 4.7.2 and 4.8 for Windows Server 2019 for x64 (KB5004228)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to resolve issues in Windows. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article for more information. After you install this item, you may have to restart your computer.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   7/15/2021 5:38:04 AM
   Title                    :   Security Intelligence Update for Microsoft Defender Antivirus - KB2267602 (Version 1.343.994.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   7/15/2021 1:05:47 AM
   Title                    :   Security Intelligence Update for Microsoft Defender Antivirus - KB2267602 (Version 1.343.957.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   7/14/2021 1:05:46 AM
   Title                    :   Security Intelligence Update for Microsoft Defender Antivirus - KB2267602 (Version 1.343.916.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   7/13/2021 10:48:58 PM
   Title                    :   Security Intelligence Update for Microsoft Defender Antivirus - KB2267602 (Version 1.343.910.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   1/26/2020 4:58:30 AM
   Title                    :   Security Intelligence Update for Windows Defender Antivirus - KB2267602 (Version 1.307.3003.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   1/25/2020 6:46:15 AM
   Title                    :   Security Intelligence Update for Windows Defender Antivirus - KB2267602 (Version 1.307.2945.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB4534273
   Installed At (UTC)       :   1/24/2020 3:09:34 AM
   Title                    :   2020-01 Cumulative Update for Windows Server 2019 (1809) for x64-based Systems (KB4534273)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to resolve issues in Windows. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article for more information. After you install this item, you may have to restart your computer.

   =================================================================================================

   HotFix ID                :
   Installed At (UTC)       :   1/24/2020 2:58:16 AM
   Title                    :   VMware, Inc. - System - 7/11/2019 12:00:00 AM - 9.8.16.0
   Client Application ID    :   UpdateOrchestrator
   Description              :   VMware, Inc. System  driver update released in  July 2019

   =================================================================================================

   HotFix ID                :   KB4534273
   Installed At (UTC)       :   1/24/2020 2:32:08 AM
   Title                    :   2020-01 Cumulative Update for Windows Server 2019 (1809) for x64-based Systems (KB4534273)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to resolve issues in Windows. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article for more information. After you install this item, you may have to restart your computer.

   =================================================================================================

   HotFix ID                :   KB890830
   Installed At (UTC)       :   1/24/2020 2:31:56 AM
   Title                    :   Windows Malicious Software Removal Tool x64 - January 2020 (KB890830)
   Client Application ID    :   UpdateOrchestrator
   Description              :   After the download, this tool runs one time to check your computer for infection by specific, prevalent malicious software (including Blaster, Sasser, and Mydoom) and helps remove any infection that is found. If an infection is found, the tool will display a status report the next time that you start your computer. A new version of the tool will be offered every month. If you want to manually run the tool on your computer, you can download a copy from the Microsoft Download Center, or you can run an online version from microsoft.com. This tool is not a replacement for an antivirus product. To help protect your computer, you should use an antivirus product.

   =================================================================================================

   HotFix ID                :   KB4535101
   Installed At (UTC)       :   1/24/2020 2:30:14 AM
   Title                    :   2020-01 Cumulative Update for .NET Framework 3.5, 4.7.2 and 4.8 for Windows Server 2019 for x64 (KB4535101)
   Client Application ID    :   UpdateOrchestrator
   Description              :   A security issue has been identified in a Microsoft software product that could affect your system. You can help protect your system by installing this update from Microsoft. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article. After you install this update, you may have to restart your system.

   =================================================================================================

   HotFix ID                :   KB4516115
   Installed At (UTC)       :   1/24/2020 2:29:18 AM
   Title                    :   2019-09 Security Update for Adobe Flash Player for Windows Server 2019 for x64-based Systems (KB4516115)
   Client Application ID    :   UpdateOrchestrator
   Description              :   A security issue has been identified in a Microsoft software product that could affect your system. You can help protect your system by installing this update from Microsoft. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article. After you install this update, you may have to restart your system.

   =================================================================================================

   HotFix ID                :   KB4462930
   Installed At (UTC)       :   1/24/2020 2:29:14 AM
   Title                    :   Update for Adobe Flash Player for Windows Server 2019 (1809) for x64-based Systems (KB4462930)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to resolve issues in Windows. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article for more information. After you install this item, you may have to restart your computer.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   1/24/2020 2:26:38 AM
   Title                    :   Security Intelligence Update for Windows Defender Antivirus - KB2267602 (Version 1.307.2867.0)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :   KB4052623
   Installed At (UTC)       :   1/24/2020 2:26:17 AM
   Title                    :   Update for Windows Defender Antivirus antimalware platform - KB4052623 (Version 4.18.1911.3)
   Client Application ID    :   UpdateOrchestrator
   Description              :   This package will update Windows Defender Antivirus antimalware platform's components on the user machine.

   =================================================================================================

   HotFix ID                :   KB4534273
   Installed At (UTC)       :   1/24/2020 12:49:04 AM
   Title                    :   2020-01 Cumulative Update for Windows Server 2019 (1809) for x64-based Systems (KB4534273)
   Client Application ID    :   UpdateOrchestrator
   Description              :   Install this update to resolve issues in Windows. For a complete listing of the issues that are included in this update, see the associated Microsoft Knowledge Base article for more information. After you install this item, you may have to restart your computer.

   =================================================================================================

   HotFix ID                :   KB2267602
   Installed At (UTC)       :   1/23/2020 11:10:00 PM
   Title                    :   Security Intelligence Update for Windows Defender Antivirus - KB2267602 (Version 1.307.2844.0)
   Client Application ID    :   Windows Defender Antivirus (77BDAF73-B396-481F-9042-AD358843EC24)
   Description              :   Install this update to revise the files that are used to detect viruses, spyware, and other potentially unwanted software. Once you have installed this item, it cannot be removed.

   =================================================================================================

   HotFix ID                :
   Installed At (UTC)       :   1/23/2020 11:01:32 PM
   Title                    :   VMware, Inc. - System - 7/11/2019 12:00:00 AM - 9.8.16.0
   Client Application ID    :   Device Driver Retrieval Client
   Description              :   VMware, Inc. System  driver update released in  July 2019

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ System Last Shutdown Date/time (from Registry)
                                                                                                                                                                                                                                            
    Last Shutdown Date/time        :    7/26/2021 9:51:18 AM

ÉÍÍÍÍÍÍÍÍÍÍ¹ User Environment Variables
È Check for some passwords or keys in the env variables 
    COMPUTERNAME: SAUNA
    PUBLIC: C:\Users\Public
    LOCALAPPDATA: C:\Users\Administrator\AppData\Local
    PSModulePath: C:\Users\Administrator\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules
    PROCESSOR_ARCHITECTURE: AMD64
    Path: C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Users\Administrator\AppData\Local\Microsoft\WindowsApps
    CommonProgramFiles(x86): C:\Program Files (x86)\Common Files
    ProgramFiles(x86): C:\Program Files (x86)
    PROCESSOR_LEVEL: 25
    ProgramFiles: C:\Program Files
    PATHEXT: .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.CPL
    USERPROFILE: C:\Users\Administrator
    SystemRoot: C:\Windows
    ALLUSERSPROFILE: C:\ProgramData
    DriverData: C:\Windows\System32\Drivers\DriverData
    ProgramData: C:\ProgramData
    PROCESSOR_REVISION: 0101
    USERNAME: Administrator
    CommonProgramW6432: C:\Program Files\Common Files
    CommonProgramFiles: C:\Program Files\Common Files
    OS: Windows_NT
    PROCESSOR_IDENTIFIER: AMD64 Family 25 Model 1 Stepping 1, AuthenticAMD
    ComSpec: C:\Windows\system32\cmd.exe
    SystemDrive: C:
    TEMP: C:\Users\ADMINI~1\AppData\Local\Temp
    NUMBER_OF_PROCESSORS: 2
    APPDATA: C:\Users\Administrator\AppData\Roaming
    TMP: C:\Users\ADMINI~1\AppData\Local\Temp
    ProgramW6432: C:\Program Files
    windir: C:\Windows
    USERDOMAIN: EGOTISTICALBANK
    USERDNSDOMAIN: EGOTISTICAL-BANK.LOCAL

ÉÍÍÍÍÍÍÍÍÍÍ¹ System Environment Variables
È Check for some passwords or keys in the env variables 
    ComSpec: C:\Windows\system32\cmd.exe
    DriverData: C:\Windows\System32\Drivers\DriverData
    OS: Windows_NT
    Path: C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\
    PATHEXT: .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
    PROCESSOR_ARCHITECTURE: AMD64
    PSModulePath: C:\Program Files\WindowsPowerShell\Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules
    TEMP: C:\Windows\TEMP
    TMP: C:\Windows\TEMP
    USERNAME: SYSTEM
    windir: C:\Windows
    NUMBER_OF_PROCESSORS: 2
    PROCESSOR_LEVEL: 25
    PROCESSOR_IDENTIFIER: AMD64 Family 25 Model 1 Stepping 1, AuthenticAMD
    PROCESSOR_REVISION: 0101

ÉÍÍÍÍÍÍÍÍÍÍ¹ Audit Settings
È Check what is being logged 
    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ Audit Policy Settings - Classic & Advanced

ÉÍÍÍÍÍÍÍÍÍÍ¹ WEF Settings
È Windows Event Forwarding, is interesting to know were are sent the logs 
    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ LAPS Settings
È If installed, local administrator password is changed frequently and is restricted by ACL 
    LAPS Enabled: LAPS not installed

ÉÍÍÍÍÍÍÍÍÍÍ¹ Wdigest
È If enabled, plain-text crds could be stored in LSASS https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#wdigest
    Wdigest is not enabled

ÉÍÍÍÍÍÍÍÍÍÍ¹ LSA Protection
È If enabled, a driver is needed to read LSASS memory (If Secure Boot or UEFI, RunAsPPL cannot be disabled by deleting the registry key) https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#lsa-protection                                                                                                                                                                                                                                 
    LSA Protection is not enabled

ÉÍÍÍÍÍÍÍÍÍÍ¹ Credentials Guard
È If enabled, a driver is needed to read LSASS memory https://book.hacktricks.wiki/windows-hardening/stealing-credentials/credentials-protections#credentials-guard
    CredentialGuard is not enabled
    Virtualization Based Security Status:      Not enabled
    Configured:                                False
    Running:                                   False

ÉÍÍÍÍÍÍÍÍÍÍ¹ Cached Creds
È If > 0, credentials will be cached in the registry and accessible by SYSTEM user https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#cached-credentials
    cachedlogonscount is 10

ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating saved credentials in Registry (CurrentPass)

ÉÍÍÍÍÍÍÍÍÍÍ¹ AV Information
  [X] Exception: Invalid namespace 
    No AV was detected!!
    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ Windows Defender configuration
  Local Settings
  Group Policy Settings

ÉÍÍÍÍÍÍÍÍÍÍ¹ UAC Status
È If you are in the Administrators group check how to bypass the UAC https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#from-administrator-medium-to-high-integrity-level--uac-bypasss
    ConsentPromptBehaviorAdmin: 1 - PromptOnSecureDesktop
    EnableLUA: 1
    LocalAccountTokenFilterPolicy: 
    FilterAdministratorToken: 
      [*] LocalAccountTokenFilterPolicy set to 0 and FilterAdministratorToken != 1.
      [-] Only the RID-500 local admin account can be used for lateral movement.                                                                                                                                                            

ÉÍÍÍÍÍÍÍÍÍÍ¹ PowerShell Settings
    PowerShell v2 Version: 2.0
    PowerShell v5 Version: 5.1.17763.1
    PowerShell Core Version: 
    Transcription Settings: 
    Module Logging Settings: 
    Scriptblock Logging Settings: 
    PS history file: C:\Users\Administrator\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
    PS history size: 1619B

ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating PowerShell Session Settings using the registry
    Name                                   Microsoft.PowerShell
      BUILTIN\Administrators               AccessAllowed
      NT AUTHORITY\INTERACTIVE             AccessAllowed
      BUILTIN\Remote Management Users      AccessAllowed
   =================================================================================================

    Name                                   Microsoft.PowerShell.Workflow
      BUILTIN\Administrators               AccessAllowed
      BUILTIN\Remote Management Users      AccessAllowed
   =================================================================================================

    Name                                   Microsoft.PowerShell32
      BUILTIN\Administrators               AccessAllowed
      NT AUTHORITY\INTERACTIVE             AccessAllowed
      BUILTIN\Remote Management Users      AccessAllowed
   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ PS default transcripts history
È Read the PS history inside these files (if any)

ÉÍÍÍÍÍÍÍÍÍÍ¹ HKCU Internet Settings
    DisableCachingOfSSLPages: 0
    IE5_UA_Backup_Flag: 5.0
    PrivacyAdvanced: 1
    SecureProtocols: 2688
    User Agent: Mozilla/4.0 (compatible; MSIE 8.0; Win32)
    CertificateRevocation: 1
    ZonesSecurityUpgrade: System.Byte[]
    EnableNegotiate: 1
    WarnonZoneCrossing: 0
    MigrateProxy: 1
    ProxyEnable: 0

ÉÍÍÍÍÍÍÍÍÍÍ¹ HKLM Internet Settings
    ActiveXCache: C:\Windows\Downloaded Program Files
    CodeBaseSearchPath: CODEBASE
    EnablePunycode: 1
    MinorVersion: 0
    WarnOnIntranet: 1

ÉÍÍÍÍÍÍÍÍÍÍ¹ Drives Information
È Remember that you should search more info inside the other drives 
    C:\ (Type: Fixed)(Filesystem: NTFS)(Available space: 7 GB)(Permissions: Administrators [Allow: AllAccess], Users [Allow: AppendData/CreateDirectories])

ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking WSUS
È  https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#wsus
    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking KrbRelayUp
È  https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#krbrelayup
  The system is inside a domain (EGOTISTICALBANK) so it could be vulnerable.
È You can try https://github.com/Dec0ne/KrbRelayUp to escalate privileges

ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking If Inside Container
È If the binary cexecsvc.exe or associated service exists, you are inside Docker 
You are NOT inside a container

ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking AlwaysInstallElevated
È  https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#alwaysinstallelevated
    AlwaysInstallElevated isn't available

ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerate LSA settings - auth packages included
                                                                                                                                                                                                                                            
    auditbasedirectories                 :       0
    auditbaseobjects                     :       0
    Bounds                               :       00-30-00-00-00-20-00-00
    crashonauditfail                     :       0
    fullprivilegeauditing                :       00
    LimitBlankPasswordUse                :       1
    NoLmHash                             :       1
    Security Packages                    :       ""
    Notification Packages                :       rassfm,scecli
    Authentication Packages              :       msv1_0
    LsaPid                               :       644
    LsaCfgFlagsDefault                   :       0
    SecureBoot                           :       1
    ProductType                          :       7
    disabledomaincreds                   :       0
    everyoneincludesanonymous            :       0
    forceguest                           :       0
    restrictanonymous                    :       0
    restrictanonymoussam                 :       1

ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating NTLM Settings
  LanmanCompatibilityLevel    :  (Send NTLMv2 response only - Win7+ default)
                                                                                                                                                                                                                                            

  NTLM Signing Settings                                                                                                                                                                                                                     
      ClientRequireSigning    : False
      ClientNegotiateSigning  : True
      ServerRequireSigning    : True
      ServerNegotiateSigning  : True
      LdapSigning             : Negotiate signing (Negotiate signing)

  Session Security                                                                                                                                                                                                                          
      NTLMMinClientSec        : 536870912 (Require 128-bit encryption)
      NTLMMinServerSec        : 536870912 (Require 128-bit encryption)
                                                                                                                                                                                                                                            

  NTLM Auditing and Restrictions                                                                                                                                                                                                            
      InboundRestrictions     :  (Not defined)
      OutboundRestrictions    :  (Not defined)
      InboundAuditing         :  (Not defined)
      OutboundExceptions      :

ÉÍÍÍÍÍÍÍÍÍÍ¹ Display Local Group Policy settings - local users/machine
   Type             :     user
   Display Name     :     Local Group Policy
   Name             :     Local Group Policy
   Extensions       :     [{35378EAC-683F-11D2-A89A-00C04FBBCFA2}{D02B1F73-3407-48AE-BA88-E8213C6761F1}]
   File Sys Path    :     C:\Windows\System32\GroupPolicy\User
   Link             :     Local
   GPO Link         :     Local Machine
   Options          :     All Sections Enabled

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking AppLocker effective policy
   AppLockerPolicy version: 1
   listing rules:



ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating Printers (WMI)
      Name:                    RICOH Aficio SP 8300DN PCL 6
      Status:                  Unknown
      Sddl:                    O:SYD:(A;;LCSWSDRCWDWO;;;LA)(A;OIIO;RPWPSDRCWDWO;;;LA)(A;OIIO;GA;;;CO)(A;OIIO;GA;;;AC)(A;;SWRC;;;WD)(A;CIIO;GX;;;WD)(A;;SWRC;;;AC)(A;CIIO;GX;;;AC)(A;;LCSWDTSDRCWDWO;;;BA)(A;OICIIO;GA;;;BA)(A;OIIO;GA;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;;SWRC;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;CIIO;GX;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;;LCSWDTSDRCWDWO;;;PO)(A;OICIIO;GA;;;PO)(A;;LCSWDTSDRCWDWO;;;SO)(A;OICIIO;GA;;;SO)
      Is default:              False
      Is network printer:      False

   =================================================================================================

      Name:                    Microsoft XPS Document Writer
      Status:                  Unknown
      Sddl:                    O:SYD:(A;;LCSWSDRCWDWO;;;LA)(A;OIIO;RPWPSDRCWDWO;;;LA)(A;OIIO;GA;;;CO)(A;OIIO;GA;;;AC)(A;;SWRC;;;WD)(A;CIIO;GX;;;WD)(A;;SWRC;;;AC)(A;CIIO;GX;;;AC)(A;;LCSWDTSDRCWDWO;;;BA)(A;OICIIO;GA;;;BA)(A;OIIO;GA;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;;SWRC;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;CIIO;GX;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)
      Is default:              False
      Is network printer:      False

   =================================================================================================

      Name:                    Microsoft Print to PDF
      Status:                  Unknown
      Sddl:                    O:SYD:(A;;LCSWSDRCWDWO;;;LA)(A;OIIO;RPWPSDRCWDWO;;;LA)(A;OIIO;GA;;;CO)(A;OIIO;GA;;;AC)(A;;SWRC;;;WD)(A;CIIO;GX;;;WD)(A;;SWRC;;;AC)(A;CIIO;GX;;;AC)(A;;LCSWDTSDRCWDWO;;;BA)(A;OICIIO;GA;;;BA)(A;OIIO;GA;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;;SWRC;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;CIIO;GX;;;S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)
      Is default:              False
      Is network printer:      False

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating Named Pipes
  Name                                                                                                 CurrentUserPerms                                                       Sddl

  eventlog                                                                                             Everyone [Allow: WriteData/CreateFiles]                                O:LSG:LSD:P(A;;0x12019b;;;WD)(A;;CC;;;OW)(A;;0x12008f;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)

  ROUTER                                                                                               Everyone [Allow: WriteData/CreateFiles]                                O:SYG:SYD:P(A;;0x12019b;;;WD)(A;;0x12019b;;;AN)(A;;FA;;;SY)

  RpcProxy\49673                                                                                       Everyone [Allow: WriteData/CreateFiles], Administrators [Allow: AllAccess] O:BAG:SYD:(A;;0x12019b;;;WD)(A;;0x12019b;;;AN)(A;;FA;;;BA)

  RpcProxy\593                                                                                         Everyone [Allow: WriteData/CreateFiles]                                O:NSG:NSD:(A;;0x12019b;;;WD)(A;;RC;;;OW)(A;;0x12019b;;;AN)(A;;FA;;;S-1-5-80-521322694-906040134-3864710659-1525148216-3451224162)(A;;FA;;;S-1-5-80-979556362-403687129-3954533659-2335141334-1547273080)

  vgauth-service                                                                                       Everyone [Allow: WriteData/CreateFiles], Administrators [Allow: AllAccess] O:BAG:SYD:P(A;;0x12019f;;;WD)(A;;FA;;;SY)(A;;FA;;;BA)

  Winsock2\CatalogChangeListener-284-0                                                                 Network [Deny: WriteData/CreateFiles], Administrators [Allow: WriteData/CreateFiles] O:BAG:SYD:(D;;FW;;;NU)(A;;0x120196;;;SY)(A;;0x120196;;;BA)(A;;0x120196;;;SO)


ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating AMSI registered providers
    Provider:       {2781761E-28E0-4109-99FE-B9D127C57AFE}
    Path:           "C:\ProgramData\Microsoft\Windows Defender\platform\4.18.1911.3-0\MpOav.dll"

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating Sysmon configuration
      Installed:                False
      Hashing Algorithm:        Not Defined
      Options:                  Not Defined
      Rules:

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Enumerating Sysmon process creation logs (1)
      Unable to query Sysmon event logs, Sysmon likely not installed.

ÉÍÍÍÍÍÍÍÍÍÍ¹ Installed .NET versions
                                                                                                                                                                                                                                            
  CLR Versions
   4.0.30319

  .NET Versions                                                                                                                                                                                                                             
   4.7.03190

  .NET & AMSI (Anti-Malware Scan Interface) support                                                                                                                                                                                         
      .NET version supports AMSI     : False
      OS supports AMSI               : True

       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/
```


## eventsinfo
イベントログを大量に出力するのでだいぶノイズ
```sh
*Evil-WinRM* PS C:\Users\Administrator\Documents> .\winPEASx64.exe quiet eventsinfo
 [!] If you want to run the file analysis checks (search sensitive information in files), you need to specify the 'fileanalysis' or 'all' argument. Note that this search might take several minutes. For help, run winpeass.exe --help
ANSI color bit for Windows is not set. If you are executing this from a Windows terminal inside the host you should run 'REG ADD HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
Long paths are disabled, so the maximum length of a path supported is 260 chars (this may cause false negatives when looking for files). If you are admin, you can enable it with 'REG ADD HKLM\SYSTEM\CurrentControlSet\Control\FileSystem /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
  WinPEAS-ng by @hacktricks_live

       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/                                                                                                                                                  
                                                                                                                                                                                                                                            
  [+] Legend:
         Red                Indicates a special privilege over an object or something is misconfigured
         Green              Indicates that some protection is enabled or something is well configured
         Cyan               Indicates active users
         Blue               Indicates disabled users
         LightYellow        Indicates links

 You can find a Windows local PE Checklist here: https://book.hacktricks.wiki/en/windows-hardening/checklist-windows-privilege-escalation.html
   Creating Dynamic lists, this could take a while, please wait...                                                                                                                                                                          
   - Loading sensitive_files yaml definitions file...
   - Loading regexes yaml definitions file...
   - Checking if domain...
   - Getting Win32_UserAccount info...
   - Creating current user groups list...
   - Creating active users list (local only)...
   - Creating disabled users list...
   - Admin users list...
   - Creating AppLocker bypass list...
   - Creating files/directories list for search...
        [skipped, file search is disabled]


ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹ Interesting Events information ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ

ÉÍÍÍÍÍÍÍÍÍÍ¹ Printing Explicit Credential Events (4648) for last 30 days - A process logged on using plaintext credentials
                                                                                                                                                                                                                                            
  Subject User       :         SAUNA$
  Subject Domain     :         EGOTISTICALBANK                                                                                                                                                                                              
  Created (UTC)      :         8/9/2025 11:44:55 AM                                                                                                                                                                                         
  IP Address         :         -                                                                                                                                                                                                            
  Process            :         C:\Program Files\VMware\VMware Tools\vmtoolsd.exe                                                                                                                                                            
  Target User        :         Administrator                                                                                                                                                                                                
  Target Domain      :         EGOTISTICALBANK                                                                                                                                                                                              
                                                                                                                                                                                                                                            
   =================================================================================================

省略

ÉÍÍÍÍÍÍÍÍÍÍ¹ Printing Account Logon Events (4624) for the last 10 days.
                                                                                                                                                                                                                                            
  Subject User Name            :       -
  Subject Domain Name          :       -                                                                                                                                                                                                    
  Created (Utc)                :       8/9/2025 2:36:33 PM                                                                                                                                                                                  
  IP Address                   :       -                                                                                                                                                                                                    
  Authentication Package       :       NTLM                                                                                                                                                                                                 
  Lm Package                   :       NTLM V2                                                                                                                                                                                              
  Logon Type                   :       Network                                                                                                                                                                                              
  Target User Name             :       Administrator                                                                                                                                                                                        
  Target Domain Name           :       EGOTISTICALBANK                                                                                                                                                                                      
  Target Outbound User Name    :       -                                                                                                                                                                                                    
  Target Outbound Domain Name  :       -                                                                                                                                                                                                    
                                                                                                                                                                                                                                            
   =================================================================================================

省略

  NTLM relay might be possible - other users authenticate to this machine using NTLM!

  Accounts authenticate to this machine using NTLM v2!                                                                                                                                                                                      
  You can obtain NetNTLMv2 for these accounts by sniffing NTLM challenge/responses.
  You can then try and crack their passwords.
                                                                                                                                                                                                                                            
    EGOTISTICALBANK\Administrator
    EGOTISTICALBANK\FSmith
    EGOTISTICALBANK\svc_loanmgr

ÉÍÍÍÍÍÍÍÍÍÍ¹ Process creation events - searching logs (EID 4688) for sensitive data.
                                                                                                                                                                                                                                            

ÉÍÍÍÍÍÍÍÍÍÍ¹ PowerShell events - script block logs (EID 4104) - searching for sensitive data.
                                                                                                                                                                                                                                            

ÉÍÍÍÍÍÍÍÍÍÍ¹ Displaying Power off/on events for last 5 days
                                                                                                                                                                                                                                            
  8/9/2025 4:43:27 AM     :  Startup

       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/    
```


## userinfo
```sh
*Evil-WinRM* PS C:\Users\Administrator\Documents> .\winPEASx64.exe quiet userinfo
 [!] If you want to run the file analysis checks (search sensitive information in files), you need to specify the 'fileanalysis' or 'all' argument. Note that this search might take several minutes. For help, run winpeass.exe --help
ANSI color bit for Windows is not set. If you are executing this from a Windows terminal inside the host you should run 'REG ADD HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
Long paths are disabled, so the maximum length of a path supported is 260 chars (this may cause false negatives when looking for files). If you are admin, you can enable it with 'REG ADD HKLM\SYSTEM\CurrentControlSet\Control\FileSystem /v VirtualTerminalLevel /t REG_DWORD /d 1' and then start a new CMD
  WinPEAS-ng by @hacktricks_live

       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/                                                                                                                                                  
                                                                                                                                                                                                                                            
  [+] Legend:
         Red                Indicates a special privilege over an object or something is misconfigured
         Green              Indicates that some protection is enabled or something is well configured
         Cyan               Indicates active users
         Blue               Indicates disabled users
         LightYellow        Indicates links

 You can find a Windows local PE Checklist here: https://book.hacktricks.wiki/en/windows-hardening/checklist-windows-privilege-escalation.html
   Creating Dynamic lists, this could take a while, please wait...                                                                                                                                                                          
   - Loading sensitive_files yaml definitions file...
   - Loading regexes yaml definitions file...
   - Checking if domain...
   - Getting Win32_UserAccount info...
   - Creating current user groups list...
   - Creating active users list (local only)...
   - Creating disabled users list...
   - Admin users list...
   - Creating AppLocker bypass list...
   - Creating files/directories list for search...
        [skipped, file search is disabled]


ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹ Users Information ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ

ÉÍÍÍÍÍÍÍÍÍÍ¹ Users
È Check if you have some admin equivalent privileges https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#users--groups
  Current user: Administrator
  Current groups: Domain Users, Everyone, Administrators, Users, Builtin\Pre-Windows 2000 Compatible Access, Network, Authenticated Users, This Organization, Group Policy Creator Owners, Domain Admins, Schema Admins, Enterprise Admins, Denied RODC Password Replication Group, NTLM Authentication
   =================================================================================================

    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ Current User Idle Time
   Current User   :     EGOTISTICALBANK\Administrator
   Idle Time      :     02h:52m:01s:234ms

ÉÍÍÍÍÍÍÍÍÍÍ¹ Display Tenant information (DsRegCmd.exe /status)
   Tenant is NOT Azure AD Joined.

ÉÍÍÍÍÍÍÍÍÍÍ¹ Current Token privileges
È Check if you can escalate privilege using some enabled token https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#token-manipulation
    SeIncreaseQuotaPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeMachineAccountPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeSecurityPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeTakeOwnershipPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeLoadDriverPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeSystemProfilePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeSystemtimePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeProfileSingleProcessPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeIncreaseBasePriorityPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeCreatePagefilePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeBackupPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeRestorePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeShutdownPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeDebugPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeSystemEnvironmentPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeChangeNotifyPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeRemoteShutdownPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeUndockPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeEnableDelegationPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeManageVolumePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeImpersonatePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeCreateGlobalPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeIncreaseWorkingSetPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeTimeZonePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeCreateSymbolicLinkPrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED
    SeDelegateSessionUserImpersonatePrivilege: SE_PRIVILEGE_ENABLED_BY_DEFAULT, SE_PRIVILEGE_ENABLED

ÉÍÍÍÍÍÍÍÍÍÍ¹ Clipboard text

ÉÍÍÍÍÍÍÍÍÍÍ¹ Logged users
    EGOTISTICALBANK\Administrator

ÉÍÍÍÍÍÍÍÍÍÍ¹ Display information about local users
   Computer Name           :   SAUNA
   User Name               :   Administrator
   User Id                 :   500
   Is Enabled              :   True
   User Type               :   Administrator
   Comment                 :   Built-in account for administering the computer/domain
   Last Logon              :   8/9/2025 4:44:55 AM
   Logons Count            :   133
   Password Last Set       :   7/26/2021 9:16:16 AM

   =================================================================================================

   Computer Name           :   SAUNA
   User Name               :   Guest
   User Id                 :   501
   Is Enabled              :   False
   User Type               :   Guest
   Comment                 :   Built-in account for guest access to the computer/domain
   Last Logon              :   1/1/1970 12:00:00 AM
   Logons Count            :   0
   Password Last Set       :   1/1/1970 12:00:00 AM

   =================================================================================================

   Computer Name           :   SAUNA
   User Name               :   krbtgt
   User Id                 :   502
   Is Enabled              :   False
   User Type               :   User
   Comment                 :   Key Distribution Center Service Account
   Last Logon              :   1/1/1970 12:00:00 AM
   Logons Count            :   0
   Password Last Set       :   1/22/2020 10:45:30 PM

   =================================================================================================

   Computer Name           :   SAUNA
   User Name               :   HSmith
   User Id                 :   1103
   Is Enabled              :   True
   User Type               :   User
   Comment                 :
   Last Logon              :   1/1/1970 12:00:00 AM
   Logons Count            :   0
   Password Last Set       :   1/22/2020 10:54:34 PM

   =================================================================================================

   Computer Name           :   SAUNA
   User Name               :   FSmith
   User Id                 :   1105
   Is Enabled              :   True
   User Type               :   User
   Comment                 :
   Last Logon              :   1/24/2020 3:27:55 PM
   Logons Count            :   8
   Password Last Set       :   1/23/2020 9:45:19 AM

   =================================================================================================

   Computer Name           :   SAUNA
   User Name               :   svc_loanmgr
   User Id                 :   1108
   Is Enabled              :   True
   User Type               :   User
   Comment                 :
   Last Logon              :   1/1/1970 12:00:00 AM
   Logons Count            :   0
   Password Last Set       :   1/24/2020 4:48:31 PM

   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ RDP Sessions
    Not Found

ÉÍÍÍÍÍÍÍÍÍÍ¹ Ever logged users
    EGOTISTICALBANK\Administrator
    EGOTISTICALBANK\svc_loanmgr
    EGOTISTICALBANK\FSmith

ÉÍÍÍÍÍÍÍÍÍÍ¹ Home folders found
    C:\Users\Administrator : Administrators [Allow: AllAccess], Administrator [Allow: AllAccess]
    C:\Users\All Users : Administrators [Allow: AllAccess]
    C:\Users\Default : Administrators [Allow: AllAccess]
    C:\Users\Default User : Administrators [Allow: AllAccess]
    C:\Users\FSmith : Administrators [Allow: AllAccess]
    C:\Users\Public : Administrators [Allow: AllAccess]
    C:\Users\svc_loanmgr : Administrators [Allow: AllAccess]

ÉÍÍÍÍÍÍÍÍÍÍ¹ Looking for AutoLogon credentials
    Some AutoLogon credentials were found
    DefaultDomainName             :  EGOTISTICALBANK
    DefaultUserName               :  EGOTISTICALBANK\svc_loanmanager
    DefaultPassword               :  Moneymakestheworldgoround!

ÉÍÍÍÍÍÍÍÍÍÍ¹ Password Policies
È Check for a possible brute-force 
    Domain: Builtin
    SID: S-1-5-32
    MaxPasswordAge: 42.22:47:31.7437440
    MinPasswordAge: 00:00:00
    MinPasswordLength: 0
    PasswordHistoryLength: 0
    PasswordProperties: 0
   =================================================================================================

    Domain: EGOTISTICALBANK
    SID: S-1-5-21-2966785786-3096785034-1186376766
    MaxPasswordAge: 42.00:00:00
    MinPasswordAge: 1.00:00:00
    MinPasswordLength: 7
    PasswordHistoryLength: 24
    PasswordProperties: DOMAIN_PASSWORD_COMPLEX
   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Print Logon Sessions
    Method:                       LSA
    Logon Server:                 SAUNA
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     5613909
    Logon Time:                   8/9/2025 2:35:10 PM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       NTLM
    Start Time:
    User Name:                    Administrator
    User Principal Name:          Administrator@EGOTISTICAL-BANK.LOCAL
    User SID:                     S-1-5-21-2966785786-3096785034-1186376766-500

   =================================================================================================

    Method:                       LSA
    Logon Server:                 SAUNA
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     3395198
    Logon Time:                   8/9/2025 1:45:01 PM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       NTLM
    Start Time:
    User Name:                    FSmith
    User Principal Name:          FSmith@EGOTISTICAL-BANK.LOCAL
    User SID:                     S-1-5-21-2966785786-3096785034-1186376766-1105

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     247002
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     246882
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     246627
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     246460
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     68298
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Window Manager
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    DWM-1
    User Principal Name:
    User SID:                     S-1-5-90-0-1

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     996
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Service
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-20

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     40436
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Font Driver Host
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    UMFD-1
    User Principal Name:
    User SID:                     S-1-5-96-0-1

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     40310
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Font Driver Host
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    UMFD-1
    User Principal Name:
    User SID:                     S-1-5-96-0-1

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     40288
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Font Driver Host
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    UMFD-0
    User Principal Name:
    User SID:                     S-1-5-96-0-0

   =================================================================================================

    Method:                       LSA
    Logon Server:                 SAUNA
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     3564664
    Logon Time:                   8/9/2025 2:00:32 PM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       NTLM
    Start Time:
    User Name:                    Administrator
    User Principal Name:          Administrator@EGOTISTICAL-BANK.LOCAL
    User SID:                     S-1-5-21-2966785786-3096785034-1186376766-500

   =================================================================================================

    Method:                       LSA
    Logon Server:                 SAUNA
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     3466776
    Logon Time:                   8/9/2025 1:51:49 PM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       NTLM
    Start Time:
    User Name:                    Administrator
    User Principal Name:          Administrator@EGOTISTICAL-BANK.LOCAL
    User SID:                     S-1-5-21-2966785786-3096785034-1186376766-500

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     1625764
    Logon Time:                   8/9/2025 11:58:46 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     246770
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     246226
    Logon Time:                   8/9/2025 11:44:16 AM
    Logon Type:                   Network
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Kerberos
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:
    User SID:                     S-1-5-18

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     995
    Logon Time:                   8/9/2025 11:44:05 AM
    Logon Type:                   Service
    Start Time:
    Domain:                       NT AUTHORITY
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    IUSR
    User Principal Name:
    User SID:                     S-1-5-17

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     997
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Service
    Start Time:
    Domain:                       NT AUTHORITY
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    LOCAL SERVICE
    User Principal Name:
    User SID:                     S-1-5-19

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     68319
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Window Manager
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    DWM-1
    User Principal Name:
    User SID:                     S-1-5-90-0-1

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:
    Logon Id:                     40431
    Logon Time:                   8/9/2025 11:43:36 AM
    Logon Type:                   Interactive
    Start Time:
    Domain:                       Font Driver Host
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    UMFD-0
    User Principal Name:
    User SID:                     S-1-5-96-0-0

   =================================================================================================

    Method:                       LSA
    Logon Server:
    Logon Server Dns Domain:      EGOTISTICAL-BANK.LOCAL
    Logon Id:                     999
    Logon Time:                   8/9/2025 11:43:34 AM
    Logon Type:                   0
    Start Time:
    Domain:                       EGOTISTICALBANK
    Authentication Package:       Negotiate
    Start Time:
    User Name:                    SAUNA$
    User Principal Name:          SAUNA$@EGOTISTICAL-BANK.LOCAL
    User SID:                     S-1-5-18

   =================================================================================================


       /---------------------------------------------------------------------------------\                                                                                                                                                  
       |                             Do you like PEASS?                                  |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |         Learn Cloud Hacking       :     training.hacktricks.xyz                 |                                                                                                                                                  
       |         Follow on Twitter         :     @hacktricks_live                        |                                                                                                                                                  
       |         Respect on HTB            :     SirBroccoli                             |                                                                                                                                                  
       |---------------------------------------------------------------------------------|                                                                                                                                                  
       |                                 Thank you!                                      |                                                                                                                                                  
       \---------------------------------------------------------------------------------/
```
