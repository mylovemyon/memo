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


## processinfo
```sh
*Evil-WinRM* PS C:\Users\Administrator\Documents> .\winPEASx64.exe quiet processinfo
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


ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹ Processes Information ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ

ÉÍÍÍÍÍÍÍÍÍÍ¹ Interesting Processes -non Microsoft-
È Check if any interesting processes for memory dump or if you could overwrite some binary running https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#running-processes
    svchost(1768)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s SENS
   =================================================================================================

    svchost(1964)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k netsvcs -p -s ShellHWDetection
   =================================================================================================

    svchost(1368)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -p -s SstpSvc
   =================================================================================================

    svchost(1564)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -p -s FontCache
   =================================================================================================

    spoolsv(2940)[C:\Windows\System32\spoolsv.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\spoolsv.exe
   =================================================================================================                                                                                                                                        

    svchost(2148)[C:\Windows\System32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k NetworkService -p -s LanmanWorkstation
   =================================================================================================

    LogonUI(4904)[C:\Windows\system32\LogonUI.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: "LogonUI.exe" /flags:0x2 /state0:0xa3a0c055 /state1:0x41c64e6d
   =================================================================================================                                                                                                                                        

    svchost(4164)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s UsoSvc
   =================================================================================================

    svchost(1956)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s UserManager
   =================================================================================================

    svchost(1352)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNoNetworkFirewall -p
   =================================================================================================

    svchost(952)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k DcomLaunch -p -s LSM
   =================================================================================================

    svchost(1148)[C:\Windows\system32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k NetworkService -p -s Dnscache
   =================================================================================================

    winlogon(552)[C:\Windows\system32\winlogon.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: winlogon.exe
   =================================================================================================                                                                                                                                        

    svchost(1528)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s Schedule
   =================================================================================================

    svchost(1132)[C:\Windows\System32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted -p -s EventLog
   =================================================================================================

    svchost(2508)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted -p -s SysMain
   =================================================================================================

    svchost(340)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s DsmSvc
   =================================================================================================

    svchost(3096)[C:\Windows\System32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k NetworkService -p -s tapisrv
   =================================================================================================

    svchost(5088)[C:\Windows\System32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalService -p -s LicenseManager
   =================================================================================================

    svchost(1316)[C:\Windows\System32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k NetworkService -p -s NlaSvc
   =================================================================================================

    svchost(1848)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted -p -s WinHttpAutoProxySvc
   =================================================================================================

    svchost(1904)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s Winmgmt
   =================================================================================================

    svchost(720)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s WpnService
   =================================================================================================

    svchost(716)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -p -s nsi
   =================================================================================================

    msdtc(3864)[C:\Windows\System32\msdtc.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\msdtc.exe
   =================================================================================================                                                                                                                                        

    svchost(1060)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted -p -s UALSVC
   =================================================================================================

    vmtoolsd(2676)[C:\Program Files\VMware\VMware Tools\vmtoolsd.exe] -- POwn: SYSTEM
    Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking folder: C:\Program Files\VMware\VMware Tools (Administrators [Allow: AllAccess])
    Command Line: "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe"
   =================================================================================================                                                                                                                                        

    svchost(1096)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted -p -s Dhcp
   =================================================================================================

    winPEASx64(2276)[C:\Users\Administrator\Documents\winPEASx64.exe] -- POwn: Administrator -- isDotNet
    Permissions: Administrators [Allow: AllAccess], Administrator [Allow: AllAccess]
    Possible DLL Hijacking folder: C:\Users\Administrator\Documents (Administrators [Allow: AllAccess], Administrator [Allow: AllAccess])
    Command Line: "C:\Users\Administrator\Documents\winPEASx64.exe" quiet processinfo
   =================================================================================================                                                                                                                                        

    svchost(896)[C:\Windows\system32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k RPCSS -p
   =================================================================================================

    svchost(1880)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k utcsvc -p
   =================================================================================================

    dns(2076)[C:\Windows\system32\dns.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\dns.exe
   =================================================================================================                                                                                                                                        

    svchost(1484)[C:\Windows\System32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalService -p -s netprofm
   =================================================================================================

    dfsrs(3052)[C:\Windows\system32\DFSRs.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\DFSRs.exe
   =================================================================================================                                                                                                                                        

    fontdrvhost(2852)[C:\Windows\system32\fontdrvhost.exe] -- POwn: UMFD-1
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: "fontdrvhost.exe"
   =================================================================================================                                                                                                                                        

    fontdrvhost(2848)[C:\Windows\system32\fontdrvhost.exe] -- POwn: UMFD-0
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: "fontdrvhost.exe"
   =================================================================================================                                                                                                                                        

    svchost(4620)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k netsvcs
   =================================================================================================

    svchost(1664)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k netsvcs -p -s Themes
   =================================================================================================

    WmiPrvSE(3632)[C:\Windows\system32\wbem\wmiprvse.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32\wbem (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\wbem\wmiprvse.exe
   =================================================================================================                                                                                                                                        

    svchost(2636)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k iissvcs
   =================================================================================================

    svchost(1656)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -p -s EventSystem
   =================================================================================================

    ismserv(2440)[C:\Windows\System32\ismserv.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\ismserv.exe
   =================================================================================================                                                                                                                                        

    svchost(860)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k DcomLaunch -p
   =================================================================================================

    svchost(660)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -s W32Time
   =================================================================================================

    conhost(68)[C:\Windows\system32\conhost.exe] -- POwn: Administrator
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: \??\C:\Windows\system32\conhost.exe 0x4
   =================================================================================================

    svchost(1052)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted -p -s TimeBrokerSvc
   =================================================================================================

    svchost(1684)[C:\Windows\System32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalServiceNoNetwork -p -s DPS
   =================================================================================================

    svchost(1636)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s ProfSvc
   =================================================================================================

    svchost(1832)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNetworkRestricted -p
   =================================================================================================

    svchost(2028)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k NetSvcs -p -s iphlpsvc
   =================================================================================================

    svchost(1044)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted -p -s NcbService
   =================================================================================================

    lsass(644)[C:\Windows\system32\lsass.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\lsass.exe
   =================================================================================================                                                                                                                                        

    svchost(840)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k DcomLaunch -p -s PlugPlay
   =================================================================================================

    svchost(3004)[C:\Windows\system32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k NetworkService -p -s CryptSvc
   =================================================================================================

    svchost(2608)[C:\Windows\system32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k NetworkServiceNetworkRestricted -p -s PolicyAgent
   =================================================================================================

    svchost(636)[C:\Windows\System32\svchost.exe] -- POwn: NETWORK SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k NetworkService -p -s WinRM
   =================================================================================================

    svchost(4328)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted -p -s StorSvc
   =================================================================================================

    dllhost(3732)[C:\Windows\system32\dllhost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\dllhost.exe /Processid:{02D4B3F1-FD88-11D1-960D-00805FC79235}
   =================================================================================================

    svchost(2992)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork -p
   =================================================================================================

    VGAuthService(2396)[C:\Program Files\VMware\VMware Tools\VMware VGAuth\VGAuthService.exe] -- POwn: SYSTEM
    Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking folder: C:\Program Files\VMware\VMware Tools\VMware VGAuth (Administrators [Allow: AllAccess])
    Command Line: "C:\Program Files\VMware\VMware Tools\VMware VGAuth\VGAuthService.exe"
   =================================================================================================                                                                                                                                        

    Microsoft.ActiveDirectory.WebServices(2984)[C:\Windows\ADWS\Microsoft.ActiveDirectory.WebServices.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\ADWS (Administrators [Allow: AllAccess])
    Command Line: C:\Windows\ADWS\Microsoft.ActiveDirectory.WebServices.exe
   =================================================================================================                                                                                                                                        

    dwm(1012)[C:\Windows\system32\dwm.exe] -- POwn: DWM-1
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: "dwm.exe"
   =================================================================================================                                                                                                                                        

    svchost(3768)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalSystemNetworkRestricted -p -s DsSvc
   =================================================================================================

    svchost(2704)[C:\Windows\System32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k smbsvcs -s LanmanServer
   =================================================================================================

    svchost(2976)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k apphost -s AppHostSvc
   =================================================================================================

    wsmprovhost(4512)[C:\Windows\system32\wsmprovhost.exe] -- POwn: Administrator
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\wsmprovhost.exe -Embedding
   =================================================================================================

    vm3dservice(1476)[C:\Windows\system32\vm3dservice.exe] -- POwn: SYSTEM
    Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\vm3dservice.exe
   =================================================================================================                                                                                                                                        

    svchost(804)[C:\Windows\System32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\System32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\System32\svchost.exe -k LocalServiceNetworkRestricted -p -s lmhosts
   =================================================================================================

    dfssvc(3084)[C:\Windows\system32\dfssvc.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\dfssvc.exe
   =================================================================================================                                                                                                                                        

    svchost(800)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalSystemNetworkRestricted -p -s PcaSvc
   =================================================================================================

    svchost(4144)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s wuauserv
   =================================================================================================

    svchost(1384)[C:\Windows\system32\svchost.exe] -- POwn: SYSTEM
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k netsvcs -p -s gpsvc
   =================================================================================================

    svchost(1184)[C:\Windows\system32\svchost.exe] -- POwn: LOCAL SERVICE
    Possible DLL Hijacking folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Command Line: C:\Windows\system32\svchost.exe -k LocalService -p -s CDPSvc
   =================================================================================================


ÉÍÍÍÍÍÍÍÍÍÍ¹ Vulnerable Leaked Handlers
È  https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#leaked-handlers
È Getting Leaked Handlers, it might take some time...
                   
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


## servicesinfo
```sh
*Evil-WinRM* PS C:\Users\Administrator\Documents> .\winPEASx64.exe quiet servicesinfo
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


ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹ Services Information ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ

ÉÍÍÍÍÍÍÍÍÍÍ¹ Interesting Services -non Microsoft-
È Check if you can overwrite some service binary or perform a DLL hijacking, also check for unquoted paths https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#services
    ssh-agent(OpenSSH Authentication Agent)[C:\Windows\System32\OpenSSH\ssh-agent.exe] - Disabled - Stopped
    YOU CAN MODIFY THIS SERVICE: Start, AllAccess
    Possible DLL Hijacking in binary folder: C:\Windows\System32\OpenSSH (Administrators [Allow: WriteData/CreateFiles])
    Agent to hold private keys used for public key authentication.
   =================================================================================================                                                                                                                                        

    VGAuthService(VMware, Inc. - VMware Alias Manager and Ticket Service)["C:\Program Files\VMware\VMware Tools\VMware VGAuth\VGAuthService.exe"] - Auto - Running
    YOU CAN MODIFY THIS SERVICE: AllAccess
    File Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking in binary folder: C:\Program Files\VMware\VMware Tools\VMware VGAuth (Administrators [Allow: AllAccess])
    Alias Manager and Ticket Service
   =================================================================================================                                                                                                                                        

    vm3dservice(VMware, Inc. - VMware SVGA Helper Service)[C:\Windows\system32\vm3dservice.exe] - Auto - Running
    YOU CAN MODIFY THIS SERVICE: AllAccess
    File Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking in binary folder: C:\Windows\system32 (Administrators [Allow: WriteData/CreateFiles])
    Helps VMware SVGA driver by collecting and conveying user mode information
   =================================================================================================                                                                                                                                        

    VMTools(VMware, Inc. - VMware Tools)["C:\Program Files\VMware\VMware Tools\vmtoolsd.exe"] - Auto - Running
    YOU CAN MODIFY THIS SERVICE: AllAccess
    File Permissions: Administrators [Allow: AllAccess]
    Possible DLL Hijacking in binary folder: C:\Program Files\VMware\VMware Tools (Administrators [Allow: AllAccess])
    Provides support for synchronizing objects between the host and guest operating systems.
   =================================================================================================                                                                                                                                        


ÉÍÍÍÍÍÍÍÍÍÍ¹ Modifiable Services
È Check if you can modify any service https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#services
    LOOKS LIKE YOU CAN MODIFY OR START/STOP SOME SERVICE/s:
    ADWS: AllAccess
    AJRouter: AllAccess
    ALG: AllAccess
    AppHostSvc: AllAccess
    AppIDSvc: AllAccess
    Appinfo: AllAccess
    AppMgmt: AllAccess
    AppReadiness: AllAccess
    AppVClient: Start, AllAccess
    AppXSvc: GenericExecute (Start/Stop)
    AudioEndpointBuilder: AllAccess
    Audiosrv: AllAccess
    AxInstSV: AllAccess
    BFE: WriteDac
    BITS: AllAccess
    BrokerInfrastructure: WriteDac, Start
    BTAGService: AllAccess
    BthAvctpSvc: AllAccess
    bthserv: AllAccess
    camsvc: AllAccess
    CDPSvc: AllAccess
    CertPropSvc: ChangeConfig
    ClipSVC: Start, WriteDac
    COMSysApp: AllAccess
    CoreMessagingRegistrar: GenericExecute (Start/Stop)
    CryptSvc: AllAccess
    CscService: AllAccess
    DcomLaunch: WriteDac
    defragsvc: AllAccess
    DeviceAssociationService: AllAccess
    DeviceInstall: AllAccess
    DevQueryBroker: AllAccess
    Dfs: AllAccess
    DFSR: AllAccess
    Dhcp: AllAccess
    diagnosticshub.standardcollector.service: AllAccess
    DiagTrack: AllAccess
    DmEnrollmentSvc: AllAccess
    dmwappushservice: Start, AllAccess
    DNS: AllAccess
    DoSvc: Start, AllAccess
    dot3svc: AllAccess
    DPS: ChangeConfig
    DsmSvc: AllAccess, Start
    DsRoleSvc: AllAccess
    DsSvc: Start, AllAccess
    Eaphost: AllAccess
    EFS: Start, ChangeConfig
    embeddedmode: GenericExecute (Start/Stop)
    EntAppSvc: GenericExecute (Start/Stop)
    EventLog: AllAccess
    EventSystem: AllAccess
    fdPHost: AllAccess
    FDResPub: AllAccess
    FontCache: AllAccess
    FrameServer: AllAccess
    GraphicsPerfSvc: AllAccess
    hidserv: AllAccess
    HvHost: AllAccess
    icssvc: Start, AllAccess
    IKEEXT: AllAccess
    InstallService: AllAccess
    iphlpsvc: AllAccess
    IsmServ: AllAccess
    Kdc: AllAccess
    KdsSvc: AllAccess
    KeyIso: AllAccess
    KPSSVC: AllAccess
    KtmRm: AllAccess
    LanmanServer: AllAccess
    LanmanWorkstation: AllAccess
    lfsvc: AllAccess
    LicenseManager: AllAccess
    lltdsvc: AllAccess
    lmhosts: AllAccess
    MapsBroker: Start, AllAccess
    mpssvc: WriteDac
    MSDTC: ChangeConfig
    MSiSCSI: AllAccess
    msiserver: GenericExecute (Start/Stop)
    NcaSvc: AllAccess
    NcbService: AllAccess
    Netlogon: AllAccess
    Netman: AllAccess
    netprofm: AllAccess
    NetSetupSvc: AllAccess, Start
    NetTcpPortSharing: AllAccess
    NgcCtnrSvc: WriteDac
    NgcSvc: WriteDac
    NlaSvc: AllAccess
    nsi: AllAccess
    NTDS: AllAccess
    NtFrs: AllAccess
    PcaSvc: AllAccess
    PerfHost: AllAccess
    PhoneSvc: Start, AllAccess
    pla: Start, AllAccess
    PlugPlay: AllAccess
    PolicyAgent: AllAccess
    Power: AllAccess
    PrintNotify: AllAccess
    ProfSvc: AllAccess
    PushToInstall: AllAccess
    QWAVE: AllAccess
    RasAuto: AllAccess
    RasMan: Start, AllAccess
    RemoteAccess: AllAccess
    RemoteRegistry: AllAccess
    RmSvc: ChangeConfig, GenericExecute (Start/Stop)
    RpcEptMapper: WriteDac, Start
    RpcLocator: AllAccess
    RpcSs: WriteDac
    RSoPProv: AllAccess
    sacsvr: AllAccess
    SamSs: AllAccess
    SCardSvr: ChangeConfig
    ScDeviceEnum: ChangeConfig
    Schedule: WriteDac
    SCPolicySvc: ChangeConfig
    seclogon: Start, AllAccess
    SEMgrSvc: AllAccess
    SENS: AllAccess
    Sense: ChangeConfig
    SensorDataService: AllAccess
    SensorService: Start, AllAccess
    SensrSvc: Start, AllAccess
    SessionEnv: AllAccess
    SgrmBroker: AllAccess
    SharedAccess: AllAccess
    ShellHWDetection: AllAccess
    shpamsvc: AllAccess
    smphost: Start, AllAccess
    SNMPTRAP: AllAccess
    Spooler: AllAccess
    sppsvc: Start, WriteDac
    SSDPSRV: AllAccess
    ssh-agent: Start, AllAccess
    SstpSvc: Start, AllAccess
    StateRepository: GenericExecute (Start/Stop)
    stisvc: AllAccess
    StorSvc: AllAccess
    svsvc: AllAccess
    swprv: AllAccess
    SysMain: AllAccess
    SystemEventsBroker: WriteDac, Start
    TabletInputService: Start, AllAccess
    tapisrv: AllAccess
    TermService: AllAccess
    Themes: AllAccess
    TieringEngineService: AllAccess
    TimeBrokerSvc: WriteDac, Start
    TokenBroker: AllAccess
    TrkWks: AllAccess
    TrustedInstaller: ChangeConfig
    tzautoupdate: AllAccess
    UALSVC: AllAccess
    UevAgentService: Start, AllAccess
    UmRdpService: AllAccess
    upnphost: AllAccess
    UserManager: AllAccess
    UsoSvc: Start, AllAccess
    VaultSvc: AllAccess
    vds: AllAccess
    VGAuthService: AllAccess
    vm3dservice: AllAccess
    vmicguestinterface: AllAccess
    vmicheartbeat: AllAccess
    vmickvpexchange: AllAccess
    vmicrdv: AllAccess
    vmicshutdown: AllAccess
    vmictimesync: AllAccess
    vmicvmsession: AllAccess
    vmicvss: AllAccess
    VMTools: AllAccess
    vmvss: AllAccess
    VSS: AllAccess
    W32Time: AllAccess
    w3logsvc: AllAccess
    W3SVC: AllAccess
    WaaSMedicSvc: Start, AllAccess
    WalletService: AllAccess
    WarpJITSvc: AllAccess
    WAS: AllAccess
    WbioSrvc: AllAccess
    Wcmsvc: AllAccess
    WdiServiceHost: ChangeConfig
    WdiSystemHost: ChangeConfig
    Wecsvc: AllAccess
    WEPHOSTSVC: AllAccess
    wercplsupport: AllAccess
    WerSvc: AllAccess
    WiaRpc: AllAccess
    Winmgmt: AllAccess
    WinRM: AllAccess
    wisvc: AllAccess
    wlidsvc: AllAccess
    wmiApSrv: AllAccess
    WMPNetworkSvc: AllAccess
    WPDBusEnum: AllAccess
    WpnService: AllAccess
    WSearch: AllAccess
    wuauserv: Start, AllAccess

ÉÍÍÍÍÍÍÍÍÍÍ¹ Looking if you can modify any service registry
È Check if you can modify the registry of a service https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#services-registry-modify-permissions
    HKLM\system\currentcontrolset\services\.NET CLR Data (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NET CLR Networking (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NET CLR Networking 4.0.0.0 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NET Data Provider for Oracle (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NET Data Provider for SqlServer (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NET Memory Cache 4.0 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\.NETFramework (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\1394ohci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\3ware (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ACPI (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AcpiDev (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\acpiex (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\acpipagr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AcpiPmi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\acpitime (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ADOVMPPackage (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ADP80XX (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\adsi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ADWS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AFD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\afunix (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ahcache (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AJRouter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ALG (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AmdK8 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AmdPPM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\amdsata (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\amdsbs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\amdxata (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppHostSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppID (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppIDSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Appinfo (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\applockerfltr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppMgmt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppReadiness (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppVClient (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppvStrm (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppvVemgr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppvVfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AppXSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\arcsas (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AsyncMac (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\atapi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AudioEndpointBuilder (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Audiosrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\AxInstSV (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\b06bdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bam (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BasicDisplay (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BasicRender (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BattC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bcmfn2 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Beep (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bfadfcoei (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bfadi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BFE (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bindflt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BITS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bowser (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BrokerInfrastructure (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BTAGService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BthAvctpSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BthEnum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BthLEEnum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BthMini (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BTHPORT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bthserv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\BTHUSB (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bttflt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\buttonconverter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bxfcoe (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\bxois (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\camsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CapImg (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CaptureService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cbdhsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cdfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CDPSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CDPUserSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cdrom (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CertPropSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cht4iscsi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cht4vbd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CldFlt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CLFS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ClipSVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\clr_optimization_v4.0.30319_32 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\clr_optimization_v4.0.30319_64 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CmBatt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CNG (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\cnghwassist (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CompositeBus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\COMSysApp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\condrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ConsentUxUserSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CoreMessagingRegistrar (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CoreUI (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\crypt32 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CryptSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CSC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\CscService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\dam (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DCLocator (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\defragsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DeviceAssociationService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DeviceInstall (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DevicePickerUserSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DevicesFlowUserSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DevQueryBroker (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Dfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Dfsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DfsDriver (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DFSR (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DfsrRo (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Dhcp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\diagnosticshub.standardcollector.service (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DiagTrack (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Disk (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DmEnrollmentSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\dmvsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\dmwappushservice (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DNS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Dnscache (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DoSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\dot3svc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\drmkaud (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DsmSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DsRoleSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DsSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\DXGKrnl (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\e1iexpress (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Eaphost (Administrators [Allow: WriteKey FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ebdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EFS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EhStorClass (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EhStorTcgDrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\elxfcoe (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\elxstor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\embeddedmode (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EntAppSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ErrDev (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ESENT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EventLog (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\EventSystem (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\exfat (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\fastfat (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\fcvsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\fdc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\fdPHost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FDResPub (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FileCrypt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FileInfo (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Filetrace (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\flpydisk (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FltMgr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FontCache (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FrameServer (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\FsDepends (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Fs_Rec (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\gencounter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\genericusbfn (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\GPIOClx0101 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\GraphicsPerfSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HDAudBus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HidBatt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hidinterrupt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hidserv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HidUsb (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HomeGroupListener (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HpSAMD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HTTP (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hvcrash (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HvHost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hvservice (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HwNClx0101 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hwpolicy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\hyperkbd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\HyperVideo (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\i8042prt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iaLPSSi_GPIO (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iaLPSSi_I2C (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iaStorAVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iaStorV (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ibbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\icssvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IKEEXT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IndirectKmd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\inetaccs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\InetInfo (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\InstallService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\intelide (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\intelpep (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\intelppm (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iorate (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IpFilterDriver (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iphlpsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IPMIDRV (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IPNAT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IPsecGW (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IPT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\isapnp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\iScsiPrt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\IsmServ (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ItSas35i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\kbdclass (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\kbdhid (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Kdc (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\kdnic (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KdsSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KeyIso (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KPSSVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KSecDD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KSecPkg (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ksthunk (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\KtmRm (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LanmanServer (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LanmanWorkstation (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ldap (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\lfsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LicenseManager (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\lltdio (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\lltdsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\lmhosts (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Lsa (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LSI_SAS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LSI_SAS2i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LSI_SAS3i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LSI_SSS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\LSM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\luafv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MapsBroker (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mausbhost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mausbip (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\megasas (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\megasas2i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\megasas35i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\megasr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Microsoft_Bluetooth_AvrcpTransport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mlx4_bus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MMCSS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Modem (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\monitor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mouclass (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mouhid (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mountmgr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mpsdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mpssvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mrxsmb (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mrxsmb20 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MsBridge (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSDTC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSDTC Bridge 4.0.0.0 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Msfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\msgpiowin32 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mshidkmdf (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mshidumdf (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\msisadrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSiSCSI (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\msiserver (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSKSSRV (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MsLbfoProvider (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MsLldp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSPCLOCK (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSPQM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MsRPC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSSCNTRS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MsSecFlt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mssmbios (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MSTEE (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\MTConfig (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Mup (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\mvumis (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\napagent (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NcaSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NcbService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ndfltr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NDIS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NdisCap (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NdisImPlatform (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NdisTapi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Ndisuio (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NdisVirtualBus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NdisWan (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ndiswanlegacy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ndproxy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetAdapterCx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetBIOS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetbiosSmb (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetBT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Netlogon (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Netman (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\netprofm (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetSetupSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NetTcpPortSharing (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\netvsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\netvscvfpp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NgcCtnrSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NgcSvc (Administrators [Allow: TakeOwnership FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NlaSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Npfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\npsvctrig (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\nsi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\nsiproxy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\NTDS (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\NtFrs (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\Ntfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Null (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\nvdimm (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\nvraid (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\nvstor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Parport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\partmgr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PcaSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pciide (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pcmcia (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pcw (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pdc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PEAUTH (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\percsas2i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\percsas3i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PerfDisk (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PerfHost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PerfNet (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PerfOS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PerfProc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PhoneSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PimIndexMaintenanceSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PktMon (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pla (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PlugPlay (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pmem (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PNPMEM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PolicyAgent (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PortProxy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Power (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PptpMiniport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PrintNotify (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PrintWorkflowUserSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Processor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ProfSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Psched (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\PushToInstall (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\pvscsi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\qebdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\qefcoe (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\qeois (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ql2300i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ql40xx2i (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\qlfcoei (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\QWAVE (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\QWAVEdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Ramdisk (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RasAcd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RasAgileVpn (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RasAuto (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\RasGre (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Rasl2tp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RasMan (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\RasPppoe (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RasSstp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\rdbss (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RDMANDK (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\rdpbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RDPDR (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RDPNP (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RDPUDD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RdpVideoMiniport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ReFS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ReFSv1 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RemoteAccess (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\RemoteRegistry (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RFCOMM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\rhproxy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RmSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RpcEptMapper (Administrators [Allow: TakeOwnership FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RpcLocator (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\RSoPProv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\rspndr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\s3cap (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sacdrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sacsvr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sbp2port (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SCardSvr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ScDeviceEnum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\scfilter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Schedule (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\scmbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SCPolicySvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sdbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SDFRd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sdstor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\seclogon (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SecurityHealthService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SEMgrSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SENS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Sense (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SensorDataService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SensorService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SensrSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SerCx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SerCx2 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Serenum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Serial (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sermouse (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SessionEnv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sfloppy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SgrmAgent (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SgrmBroker (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SharedAccess (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ShellHWDetection (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\shpamsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SiSRaid2 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SiSRaid4 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SmartPqi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SmartSAMD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\smbdirect (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\smphost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SMSvcHost 4.0.0.0 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SNMP (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SNMPTRAP (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\spaceport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SpbCx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Spooler (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\sppsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\srv2 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\srvnet (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SSDPSRV (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ssh-agent (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SstpSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\StateRepository (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\stexstor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\stisvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\storahci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\storflt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\stornvme (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\storqosflt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\StorSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\storufs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\storvsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\svsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\swenum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\swprv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Synth3dVsc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SysMain (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\SystemEventsBroker (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TabletInputService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tapisrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Tcpip (Administrators [Allow: FullControl])
    HKLM\system\currentcontrolset\services\Tcpip6 (Administrators [Allow: FullControl])
    HKLM\system\currentcontrolset\services\TCPIP6TUNNEL (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tcpipreg (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TCPIPTUNNEL (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tdx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\terminpt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TermService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Themes (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TieringEngineService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TimeBrokerSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TokenBroker (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TPM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TSDDD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TsUsbFlt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\TsUsbGD (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tsusbhub (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tunnel (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\tzautoupdate (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UALSVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UASPStor (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UcmCx0101 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UcmTcpciCx0101 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UcmUcsi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UcmUcsiAcpiClient (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UcmUcsiCx0101 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Ucx01000 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UdeCx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\udfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UEFI (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UevAgentDriver (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UevAgentService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Ufx01000 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UfxChipidea (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ufxsynopsys (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UGatherer (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UGTHRSVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\umbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UmPass (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UmRdpService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UnistoreSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\upnphost (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UrsChipidea (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UrsCx01000 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UrsSynopsys (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbccgp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbehci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbhub (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\USBHUB3 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbohci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbprint (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbser (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\USBSTOR (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\usbuhci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\USBXHCI (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UserDataSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UserManager (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\UsoSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VaultSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vdrvroot (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vds (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VerifierExt (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VGAuthService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vhdmp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vhf (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vm3dmp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vm3dmp-debug (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vm3dmp-stats (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vm3dmp_loader (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vm3dservice (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmbus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VMBusHID (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmgid (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicguestinterface (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicheartbeat (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmickvpexchange (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicrdv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicshutdown (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmictimesync (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicvmsession (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmicvss (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VMMemCtl (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmmouse (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VMTools (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmusbmouse (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmvss (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmwefifw (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vmxnet3ndis6 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\volmgr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\volmgrx (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\volsnap (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\volume (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vpci (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vsmraid (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vsock (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VSS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\VSTXRAID (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\vwifibus (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\W32Time (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\w3logsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\W3SVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WaaSMedicSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WacomPen (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WalletService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wanarp (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wanarpv6 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WarpJITSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WAS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WbioSrvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wcifs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Wcmsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wcnfs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WdBoot (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Wdf01000 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WdFilter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WdmCompanionFilter (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WdNisDrv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WdNisSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Wecsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WEPHOSTSVC (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wercplsupport (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WerSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WFPLWFS (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WiaRpc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WIMMount (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinDefend (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Windows Workflow Foundation 4.0.0.0 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WindowsTrustedRT (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WindowsTrustedRTProxy (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinHttpAutoProxySvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinMad (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Winmgmt (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\WinNat (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinQuic (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinRM (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Winsock (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinSock2 (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WINUSB (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WinVerbs (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wisvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WlanSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wlidsvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WmiAcpi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WmiApRpl (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\wmiApSrv (Administrators [Allow: GenericAll FullControl])
    HKLM\system\currentcontrolset\services\WMPNetworkSvc (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\Wof (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\workerdd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WPDBusEnum (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WpdUpFltr (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WpnService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WpnUserService (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\ws2ifsl (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WSearch (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WSearchIdxPi (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\wuauserv (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WudfPf (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\WUDFRd (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\xmlprov (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\{2A5A5439-77FF-4AB7-80C2-D1F7A1761105} (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\{68D9AEC3-1C92-431B-98CA-FA70FADFE95E} (Administrators [Allow: FullControl GenericAll])
    HKLM\system\currentcontrolset\services\{7D4DF7EF-63F6-4721-B571-B79E763935E2} (Administrators [Allow: FullControl GenericAll])

ÉÍÍÍÍÍÍÍÍÍÍ¹ Checking write permissions in PATH folders (DLL Hijacking)
È Check for DLL Hijacking in PATH folders https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html#dll-hijacking
    (DLL Hijacking) C:\Windows\system32: Administrators [Allow: WriteData/CreateFiles]
    (DLL Hijacking) C:\Windows: Administrators [Allow: WriteData/CreateFiles]
    (DLL Hijacking) C:\Windows\System32\Wbem: Administrators [Allow: WriteData/CreateFiles]
    (DLL Hijacking) C:\Windows\System32\WindowsPowerShell\v1.0\: Administrators [Allow: WriteData/CreateFiles]
    (DLL Hijacking) C:\Windows\System32\OpenSSH\: Administrators [Allow: WriteData/CreateFiles]

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
