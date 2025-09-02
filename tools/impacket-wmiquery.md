- https://learn.microsoft.com/ja-jp/windows/win32/cimwin32prov/win32-provider
- https://learn.microsoft.com/en-us/windows/win32/wmisdk/wql-sql-for-wmi


### command
```sh
└─$ impacket-wmiquery -debug 'htb.local/administrator@10.129.138.203' -hashes 'aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6'                          
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Target system is 10.129.138.203 and isFQDN is False
[+] StringBinding: \\\\FOREST[\\PIPE\\atsvc]
[+] StringBinding: FOREST[49668]
[+] StringBinding: 10.129.138.203[49668]
[+] StringBinding chosen: ncacn_ip_tcp:10.129.138.203[49668]
[!] Press help for extra shell commands
```

### Win32_AssociatedProcessorMemory
```
WQL> SELECT * FROM Win32_AssociatedProcessorMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None |
```

### Win32_AutochkSetting
```sh
WQL> SELECT * FROM Win32_AutochkSetting
| SettingID | Caption | Description | UserInputDelay | 
| Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | None | None | 10 |
```

### Win32_BaseBoard
```sh
WQL> SELECT * FROM Win32_BaseBoard
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | HostingBoard | SlotLayout | RequiresDaughterBoard | SpecialRequirements | RequirementsDescription | Product | ConfigOptions | 
| Base Board | Base Board | None | Base Board | OK | Win32_BaseBoard | Intel Corporation | None | None | None | Base Board | None | None | None | True | False | False | False | None | None | None | None | False | None | False | True | None | 440BX Desktop Reference Platform | None |
```

### Win32_BIOS
```sh
WQL> SELECT * FROM Win32_BIOS
| Caption | Description | InstallDate | Name | Status | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | OtherTargetOS | Manufacturer | BuildNumber | SerialNumber | CodeSet | IdentificationCode | LanguageEdition | PrimaryBIOS | ReleaseDate | BiosCharacteristics | InstallableLanguages | ListOfLanguages | CurrentLanguage | SMBIOSPresent | SMBIOSMajorVersion | SMBIOSMinorVersion | SMBIOSBIOSVersion | BIOSVersion | SystemBiosMajorVersion | SystemBiosMinorVersion | EmbeddedControllerMajorVersion | EmbeddedControllerMinorVersion | 
| VMW71.00V.24504846.B64.2501180334 | VMW71.00V.24504846.B64.2501180334 | None | VMW71.00V.24504846.B64.2501180334 | OK | INTEL  - 6040000 | 3 | VMW71.00V.24504846.B64.2501180334 | 0 | None | VMware, Inc. | None | VMware-42 14 dd 01 77 df ed 36-48 41 b0 f9 f7 10 45 bd | None | None | None | True | 20250118000000.000000+000 | 4 7 9 11 42 43  | None | None | None | True | 2 | 7 | VMW71.00V.24504846.B64.2501180334 | INTEL  - 6040000 VMW71.00V.24504846.B64.2501180334 VMware, Inc. - 10000  | 255 | 255 | 255 | 255 |
```

### Win32_Bus
```sh
WQL> SELECT * FROM Win32_Bus
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | BusNum | BusType | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | ACPIBus_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 17 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_11 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 11 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_2&DABA3FF&1 | None | ACPI\PNP0A03\2&DABA3FF&1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 2 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PNP_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 15 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_3 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_2 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 2 | 5 |
```

### Win32_CacheMemory
```sh
WQL> SELECT * FROM Win32_CacheMemory
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | Level | WritePolicy | CacheType | LineSize | ReplacementPolicy | ReadPolicy | FlushTimer | Associativity | Location | MaxCacheSize | InstalledSize | SupportedSRAM | CurrentSRAM | ErrorCorrectType | CacheSpeed | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 0 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 1 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 2 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 3 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 4 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 5 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None |
```

### Win32_CIMLogicalDeviceCIMDataFile
```sh
WQL> SELECT * FROM Win32_CIMLogicalDeviceCIMDataFile
| Antecedent | Dependent | Purpose | PurposeDescription | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\CMBATT.SYS" | 2 | Control Method Battery Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\E1I63X64.SYS" | 2 | Intel(R) Gigabit Adapter NDIS 6.x driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VOLMGR\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLMGR.SYS" | 2 | Volume Manager Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ATAPI.SYS" | 2 | ATAPI IDE Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ATAPI.SYS" | 2 | ATAPI IDE Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0001\\7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMGENCOUNTER.SYS" | 2 | Virtual Machine Generation Counter | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\BASICDISPLAY\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\BASICDISPLAY.SYS" | 2 | Microsoft Basic Display Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0003\\4&25EE97C0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\I8042PRT.SYS" | 2 | i8042 Port Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\AMDPPM.SYS" | 2 | Processor Device Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\AMDPPM.SYS" | 2 | Processor Device Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\COMPOSITEBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERSTORE\\FILEREPOSITORY\\COMPOSITEBUS.INF_AMD64_A140581A8F8B58B7\\COMPOSITEBUS.SYS" | 2 | Multi-Transport Composite Bus Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VDRVROOT\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VDRVROOT.SYS" | 2 | Virtual Drive Root Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\ISATAP_0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\TUNNEL.SYS" | 2 | Microsoft Tunnel Interface Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\SPACEPORT\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\SPACEPORT.SYS" | 2 | Storage Spaces Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\KDNIC\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\KDNIC.SYS" | 2 | Microsoft Kernel Debugger Network Miniport | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\LSI_SAS.SYS" | 2 | LSI Fusion-MPT SAS Driver (StorPort) | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\UMBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\UMBUS.SYS" | 2 | User-Mode Bus Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SCSI\\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\\5&1982005&0&000100" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\DISK.SYS" | 2 | PnP Disk Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7110&SUBSYS_197615AD&REV_08\\3&18D45AA6&0&38" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MSISADRV.SYS" | 2 | ISA Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\I8042PRT.SYS" | 2 | i8042 Port Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI_HAL\\PNP0C08\\0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ACPI.SYS" | 2 | ACPI Driver for NT | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\BASICRENDER\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\BASICRENDER.SYS" | 2 | Microsoft Basic Render Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000000004400" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000008100000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="DISPLAY\\DEFAULT_MONITOR\\4&31BE19FA&0&UID0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MONITOR.SYS" | 2 | Monitor Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\STORAHCI.SYS" | 2 | MS AHCI Storport Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VMWVMCIHOSTDEV\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMCI.SYS" | 2 | VMware PCI VMCI Bus Device | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7191&SUBSYS_00000000&REV_01\\3&18D45AA6&0&08" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000024300000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\NDISVIRTUALBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\NDISVIRTUALBUS.SYS" | 2 | Microsoft Virtual Network Adapter Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMCI.SYS" | 2 | VMware PCI VMCI Bus Device | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#000000002A600000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\MSSMBIOS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MSSMBIOS.SYS" | 2 | System Management BIOS Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\SYSTEM\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\SWENUM.SYS" | 2 | Plug and Play Software Device Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VM3DMP_LOADER.SYS" | 2 | VMware SVGA 3D Miniport Loader | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\INTELIDE.SYS" | 2 | Intel PCI IDE Driver |
```

### Win32_ComputerSystemProcessor
```sh
WQL> SELECT * FROM Win32_ComputerSystemProcessor
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" |
```

### Win32_DesktopMonitor
```sh
WQL> SELECT * FROM Win32_DesktopMonitor
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | DisplayType | Bandwidth | ScreenHeight | ScreenWidth | MonitorManufacturer | MonitorType | PixelsPerXLogicalInch | PixelsPerYLogicalInch | 
| Generic Non-PnP Monitor | Generic Non-PnP Monitor | None | Generic Non-PnP Monitor | OK | 8 | Win32_DesktopMonitor | 0 | False | DesktopMonitor1 | None | DISPLAY\DEFAULT_MONITOR\4&31BE19FA&0&UID0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | None | None | None | (Standard monitor types) | Generic Non-PnP Monitor | 96 | 96 |
```

### Win32_DeviceBus
```sh
WQL> SELECT * FROM Win32_DeviceBus
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_11" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0100\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0001\\7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0003\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\IP_TUNNEL_DEVICE_ROOT" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A05\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\ISATAP_0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_3" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0103\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0B00\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7110&SUBSYS_197615AD&REV_08\\3&18D45AA6&0&38" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\FIXEDBUTTON\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7190&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&00" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="DISPLAY\\DEFAULT_MONITOR\\4&31BE19FA&0&UID0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_2" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7191&SUBSYS_00000000&REV_01\\3&18D45AA6&0&08" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0800\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0001\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" |
```
