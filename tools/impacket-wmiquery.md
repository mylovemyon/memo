- https://learn.microsoft.com/en-us/windows/win32/cimwin32prov/cimwin32-wmi-providers
- https://learn.microsoft.com/en-us/windows/win32/wmisdk/wql-sql-for-wmi

# COMMAND
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





# CIM WMI Provider
### CIM_Action
省略
```sh
WQL> SELECT * FROM CIM_Action
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | ActionID | Direction | Caption | Description | Registry | EntryName | EntryValue | Root | key | 
| C_x86_Runtime_Detection | 14.12.25810 | 2 | {E3819B64-3C56-3DD7-921D-00B011AD31DE} | 19 | reg31F4ACE8A8619D39F2E77D1700A55703{7FED75A1-600C-394B-8376-712E2A8861F2} | 65535 | reg31F4ACE8A8619D39F2E77D1700A55703 | reg31F4ACE8A8619D39F2E77D1700A55703 | reg31F4ACE8A8619D39F2E77D1700A55703 | Version | v14.12.25810.00 | 2 | SOFTWARE\Microsoft\VisualStudio\14.0\VC\Runtimes\x86 | 
| Servicing_Key_ProductFamily_x86 | 14.12.25810 | 2 | {C96DC6F1-894A-33E0-A8C1-3E9E7394FA28} | 19 | reg5C3AC4DB2756A2B6BDAE7C2C44DA3EC7{7FED75A1-600C-394B-8376-712E2A8861F2} | 65535 | reg5C3AC4DB2756A2B6BDAE7C2C44DA3EC7 | reg5C3AC4DB2756A2B6BDAE7C2C44DA3EC7 | reg5C3AC4DB2756A2B6BDAE7C2C44DA3EC7 | SP | #0 | 2 | SOFTWARE\Microsoft\DevDiv\vc\Servicing\14.0 | 
| Servicing_Key_ProductEdition_x86 | 14.12.25810 | 2 | {1EA220DF-5B36-3289-B979-D06841E41888} | 19 | reg382D83E6CA16404D47254964DA752DEA{7FED75A1-600C-394B-8376-712E2A8861F2} | 65535 | reg382D83E6CA16404D47254964DA752DEA | reg382D83E6CA16404D47254964DA752DEA | reg382D83E6CA16404D47254964DA752DEA | Install | #1 | 2 | SOFTWARE\Microsoft\DevDiv\vc\Servicing\14.0\RuntimeAdditional | 

~~~
```
### CIM_ActionSequence
### CIM_ActsAsSpare
### CIM_AdjacentSlots
### CIM_AggregatePExtent
### CIM_AggregatePSExtent
### CIM_AlarmDevice
### CIM_AllocatedResource
省略
```sh
WQL> SELECT * FROM CIM_AllocatedResource
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3758096384" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" |
~
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1024" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
~~~
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967293 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
~~~
| \\FOREST\root\cimv2:Win32_DMAChannel.DMAChannel=4 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
~~~
```
### CIM_ApplicationSystem
### CIM_ApplicationSystemSoftwareFeature
### CIM_AssociatedAlarm
### CIM_AssociatedBattery
### CIM_AssociatedCooling
### CIM_AssociatedMemory
```sh
WQL> SELECT * FROM CIM_AssociatedMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
```
### CIM_AssociatedProcessorMemory
```sh
WQL> SELECT * FROM CIM_AssociatedProcessorMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None |
```
### CIM_AssociatedSensor
### CIM_AssociatedSupplyCurrentSensor
### CIM_AssociatedSupplyVoltageSensor
### CIM_BasedOn
```sh
WQL> SELECT * FROM CIM_BasedOn
| Antecedent | Dependent | StartingAddress | EndingAddress | 
| \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" | \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | 710934528 | 21473787903 |
```
### CIM_Battery
rpc上では実行できない
### CIM_BinarySensor
### CIM_BIOSElement
```sh
WQL> SELECT * FROM CIM_BIOSElement 
| Caption | Description | InstallDate | Name | Status | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | OtherTargetOS | Manufacturer | BuildNumber | SerialNumber | CodeSet | IdentificationCode | LanguageEdition | PrimaryBIOS | ReleaseDate | BiosCharacteristics | InstallableLanguages | ListOfLanguages | CurrentLanguage | SMBIOSPresent | SMBIOSMajorVersion | SMBIOSMinorVersion | SMBIOSBIOSVersion | BIOSVersion | SystemBiosMajorVersion | SystemBiosMinorVersion | EmbeddedControllerMajorVersion | EmbeddedControllerMinorVersion | 
| VMW71.00V.24504846.B64.2501180334 | VMW71.00V.24504846.B64.2501180334 | None | VMW71.00V.24504846.B64.2501180334 | OK | INTEL  - 6040000 | 3 | VMW71.00V.24504846.B64.2501180334 | 0 | None | VMware, Inc. | None | VMware-42 14 58 74 07 28 c6 fb-94 7c c9 f5 3e 1f 0f f6 | None | None | None | True | 20250118000000.000000+000 | 4 7 9 11 42 43  | None | None | None | True | 2 | 7 | VMW71.00V.24504846.B64.2501180334 | INTEL  - 6040000 VMW71.00V.24504846.B64.2501180334 VMware, Inc. - 10000  | 255 | 255 | 255 | 255 |
```
### CIM_BIOSFeature
### CIM_BIOSFeatureBIOSElements
### CIM_BIOSLoadedInNV
### CIM_BootOSFromFS
### CIM_BootSAP
### CIM_BootService
### CIM_BootServiceAccessBySAP
### CIM_CacheMemory 
```sh
WQL> SELECT * FROM CIM_CacheMemory 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | Level | WritePolicy | CacheType | LineSize | ReplacementPolicy | ReadPolicy | FlushTimer | Associativity | Location | MaxCacheSize | InstalledSize | SupportedSRAM | CurrentSRAM | ErrorCorrectType | CacheSpeed | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 0 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 1 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 2 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 3 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 4 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 5 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None |
```
### CIM_Card
```sh
WQL> SELECT * FROM CIM_Card
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | HostingBoard | SlotLayout | RequiresDaughterBoard | SpecialRequirements | RequirementsDescription | Product | ConfigOptions | 
| Base Board | Base Board | None | Base Board | OK | Win32_BaseBoard | Intel Corporation | None | None | None | Base Board | None | None | None | True | False | False | False | None | None | None | None | False | None | False | True | None | 440BX Desktop Reference Platform | None | 
```
### CIM_CardInSlot
### CIM_CardOnCard
### CIM_CDROMDrive 
### CIM_Chassis
```sh
WQL> SELECT * FROM CIM_Chassis
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | CableManagementStrategy | ServicePhilosophy | ServiceDescriptions | LockPresent | AudibleAlarm | VisibleAlarm | SecurityBreach | BreachDescription | NumberOfPowerCords | CurrentRequiredOrProduced | HeatGeneration | ChassisTypes | TypeDescriptions | SMBIOSAssetTag | SecurityStatus | 
| System Enclosure | System Enclosure | None | System Enclosure | None | Win32_SystemEnclosure | No Enclosure | None | None | None | System Enclosure 0 | N/A | None | None | True | True | True | True | None | None | None | None | None | None | None | False | True | True | 65535 | None | 65535 | None | 65535 | 1  | None | No Asset Tag | 3 | 
```
### CIM_ChassisInRack
### CIM_Check
省略
```sh
WQL> SELECT * FROM CIM_Check
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | CheckID | Description | Caption | CheckMode | Level | Condition | Feature | 
| BootCamp | None | 65535 | None | 65535 | BootCamp200{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | BootCamp | BootCamp | True | 200 | VM_TYPE<>"WS" | BootCamp | 
| AppDefense | None | 65535 | None | 65535 | AppDefense0{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | AppDefense | AppDefense | True | 0 | (VM_TYPE="WS" OR MsiNTProductType=1) | AppDefense | 
| Hgfs | None | 65535 | None | 65535 | Hgfs200{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | Hgfs | Hgfs | True | 200 | VM_TYPE="ESX" | Hgfs |

~~~
```
### CIM_Chip
```sh
WQL> SELECT * FROM CIM_Chip
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | FormFactor | MemoryType | TotalWidth | DataWidth | Speed | Capacity | BankLabel | PositionInRow | InterleavePosition | DeviceLocator | TypeDetail | InterleaveDataDepth | Attributes | ConfiguredClockSpeed | MinVoltage | MaxVoltage | ConfiguredVoltage | SMBIOSMemoryType | 
| Physical Memory | Physical Memory | None | Physical Memory | None | Win32_PhysicalMemory | VMware Virtual RAM | None | None | 00000001 | Physical Memory 0 | None | VMW-2048MB | None | True | True | True | True | 8 | 2 | 64 | 64 | None | 2147483648 | RAM slot #0 | None | None | RAM slot #0 | 128 | None | 0 | 4800 | None | None | None | 3 |
```
### CIM_ClusteringSAP 
### CIM_ClusteringService
### CIM_ClusterServiceAccessBySAP
### CIM_CollectedCollections
### CIM_CollectedMSEs
```sh
WQL> SELECT * FROM CIM_CollectedMSEs
| Collection | Member | 
| \\.\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\.\root\cimv2:Win32_Process.Handle="2480" |
```
### CIM_CollectionOfMSEs
```sh
WQL> SELECT * FROM CIM_CollectionOfMSEs
| CollectionID | Caption | Description | BasicUIRestrictions | 
| \wmi\provider\sub\system\host\job | None | None | 0 | 
| \wmi\provider\sub\system\special\host\job | None | None | 0 |
```
### CIM_CollectionOfSensors
### CIM_CollectionSetting
```sh
WQL> SELECT * FROM CIM_CollectionSetting
| Collection | Setting | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectSecLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\special\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectSecLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\special\\host\\job" |
```
### CIM_CompatibleProduct
### CIM_Component
```sh
WQL> SELECT * FROM CIM_Component WHERE GroupComponent = "Win32_Directory.Name='C:\\'"
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\bootmgr" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\BOOTNXT" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\pagefile.sys" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="c:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\$RECYCLE.BIN" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Documents and Settings" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\PerfLogs" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Program Files" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Program Files (x86)" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Recovery" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\System Volume Information" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Windows" |
```
### CIM_ComputerSystem
```sh
WQL> SELECT * FROM CIM_ComputerSystem
| Caption | Description | InstallDate | Name | Status | CreationClassName | NameFormat | PrimaryOwnerContact | PrimaryOwnerName | Roles | InitialLoadInfo | LastLoadInfo | PowerManagementSupported | PowerManagementCapabilities | PowerState | ResetCapability | AutomaticResetBootOption | AutomaticManagedPagefile | AutomaticResetCapability | BootROMSupported | BootupState | CurrentTimeZone | DNSHostName | Domain | InfraredSupported | Manufacturer | Model | NetworkServerModeEnabled | OEMLogoBitmap | SupportContactDescription | SystemStartupDelay | SystemStartupOptions | SystemStartupSetting | SystemType | UserName | DomainRole | WakeUpType | OEMStringArray | BootOptionOnLimit | BootOptionOnWatchDog | ResetCount | ResetLimit | PauseAfterReset | PowerOnPasswordStatus | KeyboardPasswordStatus | AdminPasswordStatus | FrontPanelResetStatus | ChassisBootupState | PowerSupplyState | ThermalState | DaylightInEffect | EnableDaylightSavingsTime | NumberOfProcessors | NumberOfLogicalProcessors | TotalPhysicalMemory | PartOfDomain | PCSystemType | PCSystemTypeEx | Workgroup | SystemSKUNumber | SystemFamily | ChassisSKUNumber | BootStatus | HypervisorPresent | 
| FOREST | AT/AT COMPATIBLE | None | FOREST | OK | Win32_ComputerSystem | None | None | Windows User | 323 339 350 377 389 393  | None | None | True | None | 0 | 1 | True | True | True | True | Normal boot | -420 | FOREST | htb.local | False | VMware, Inc. | VMware7,1 | True | None | None | None | None | None | x64-based PC | None | 5 | 6 | [MS_VM_CERT/SHA1/27d66596a61c48dd3dc7216fd715126e33f59ae7] Welcome to the Virtual Machine  | 3 | 3 | -1 | -1 | 3932100000 | 0 | 3 | 1 | 3 | 3 | 3 | 3 | True | True | 1 | 2 | 2146447360 | True | 1 | 1 | None | None | None | None | 0 0 0 33 31 162 0 3 2 2  | True |
```
### CIM_ComputerSystemDMA
### CIM_ComputerSystemIRQ
### CIM_ComputerSystemMappedIO
### CIM_ComputerSystemPackage
### CIM_ComputerSystemResource
```sh
WQL> SELECT * FROM CIM_ComputerSystemResource
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DMAChannel.DMAChannel=4 |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967293 | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3758096384" |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1024" |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Environment.Name="ComSpec",UserName="<SYSTEM>" | 
~~~
```
### CIM_Configuration
### CIM_ConnectedTo
### CIM_ConnectorOnPackage
### CIM_Container 
```sh
WQL> SELECT * FROM CIM_Container 
| GroupComponent | PartComponent | LocationWithinContainer | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | None |
```
### CIM_ControlledBy 
rpc上では実行できない
### CIM_Controller
```sh
WQL> SELECT * FROM CIM_Controller
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | MaxNumberControlled | ProtocolSupported | TimeOfLastReset | Manufacturer | 
| ATA Channel 0 | IDE Channel | None | ATA Channel 0 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| ATA Channel 1 | IDE Channel | None | ATA Channel 1 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| Standard SATA AHCI Controller | Standard SATA AHCI Controller | None | Standard SATA AHCI Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | None | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Standard SATA AHCI Controller | 
| Intel(R) 82371AB/EB PCI Bus Master IDE Controller | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | None | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | None | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Intel | 
| Microsoft Storage Spaces Controller | Microsoft Storage Spaces Controller | None | Microsoft Storage Spaces Controller | OK | 3 | Win32_SCSIController | 0 | False | ROOT\SPACEPORT\0000 | None | ROOT\SPACEPORT\0000 | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | None | 2 | None | None | None | 18446744073709551615 | 65535 | None | spaceport | None | None | Microsoft | 
| LSI Adapter, SAS 3000 series, 8-port with 1068 | LSI Adapter, SAS 3000 series, 8-port with 1068 | None | LSI Adapter, SAS 3000 series, 8-port with 1068 | OK | 3 | Win32_SCSIController | 0 | False | PCI\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\4&2732702B&0&00A8 | None | PCI\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\4&2732702B&0&00A8 | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | None | 2 | None | None | None | 18446744073709551615 | 65535 | None | LSI_SAS | None | None | LSI | 
| VMware SVGA 3D | VMware SVGA 3D | None | VMware SVGA 3D | OK | 3 | Win32_VideoController | 0 | False | VideoController1 | None | PCI\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\3&18D45AA6&0&78 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 65535 | None | VMware Virtual SVGA 3D Graphics Adapter | 2 | None | None | None | None | 32 | 1440 | 621 | 64 | 64 | 1 | 4 | 4294967296 | 0 | 0 | 5 | 65535 | 65535 | VMware, Inc. | n/a | 0 | False | 0 | oem6.inf | VM3D_AMD64 | vm3dum64_loader.dll,vm3dum64_loader.dll,vm3dum64_loader.dll,vm3dum_loader,vm3dum_loader,vm3dum_loader | 20180726000000.000000-000 | 8.16.1.1 | None | None | None | None | None | None | None | 1440 x 621 x 4294967296 colors | 
```
### CIM_CoolingDevice
### CIM_CopyFileAction
```sh
WQL> SELECT * FROM CIM_CopyFileAction
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | ActionID | Direction | Caption | Description | Source | Destination | DeleteAfterCopy | FileKey | 
| None | None | 65535 | None | 65535 | vmGuestLib.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | vmGuestLib.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLib.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLib.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | None | True | vmGuestLib.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | vmGuestLibJava.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | vmGuestLibJava.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLibJava.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLibJava.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | None | True | vmGuestLibJava.dll_32.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | vmGuestLib.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | vmGuestLib.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLib.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLib.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | None | True | vmGuestLib.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | vmGuestLibJava.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | vmGuestLibJava.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLibJava.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | vmGuestLibJava.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 | None | True | vmGuestLibJava.dll_64.869A7E00_8665_0000_83A8_EF0F76CF0001 |
```
### CIM_CreateDirectoryAction
```sh
WQL> SELECT * FROM CIM_CreateDirectoryAction
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | ActionID | Direction | Caption | Description | DirectoryName | 
| None | None | 65535 | None | 65535 | INSTALLDIR{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | INSTALLDIR | INSTALLDIR | INSTALLDIR | 
| None | None | 65535 | None | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 |
```
### CIM_CurrentSensor
### CIM_DataFile
省略
```sh
WQL> SELECT * FROM CIM_DataFile
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | Version | Manufacturer | 
| c:\$recycle.bin\s-1-5-21-3072663084-364016917-1341370565-500\desktop.ini | c:\$recycle.bin\s-1-5-21-3072663084-364016917-1341370565-500\desktop.ini | 20210830134828.482989-420 | c:\$recycle.bin\s-1-5-21-3072663084-364016917-1341370565-500\desktop.ini | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | CIM_LogicalFile | 20210830134828.482989-420 | False | Win32_FileSystem | NTFS | 20210830134828.482989-420 | 20210830134828.482989-420 | True | 129 | True | True | True | Configuration Settings | c:\$recycle.bin\s-1-5-21-3072663084-364016917-1341370565-500\desktop.ini | None | None | c: | \$recycle.bin\s-1-5-21-3072663084-364016917-1341370565-500\ | desktop | ini | 18809343 | None | None | 
| c:\bootmgr | c:\bootmgr | 20160716063920.048752-420 | c:\bootmgr | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | CIM_LogicalFile | 20160716063920.048752-420 | False | Win32_FileSystem | NTFS | 20161120184715.012078-480 | 20161120175907.466506-480 | True | 389408 | False | True | True | File | c:\bootmgr | None | None | c: | \ | bootmgr |  | 0 | None | None | 
| c:\bootnxt | c:\bootnxt | 20160716063920.111252-420 | c:\bootnxt | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | CIM_LogicalFile | 20160716063920.111252-420 | False | Win32_FileSystem | NTFS | 20161120184715.246456-480 | 20160716061017.401390-420 | True | 1 | True | True | True | File | c:\bootnxt | None | None | c: | \ | bootnxt |  | 18809343 | None | None |

~~~
```
### CIM_Dependency
rpc上では実行できない
### CIM_DependencyContext
### CIM_DesktopMonitor
```sh
WQL> SELECT * FROM CIM_DesktopMonitor
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | DisplayType | Bandwidth | ScreenHeight | ScreenWidth | MonitorManufacturer | MonitorType | PixelsPerXLogicalInch | PixelsPerYLogicalInch | 
| Generic Non-PnP Monitor | Generic Non-PnP Monitor | None | Generic Non-PnP Monitor | OK | 8 | Win32_DesktopMonitor | 0 | False | DesktopMonitor1 | None | DISPLAY\DEFAULT_MONITOR\4&31BE19FA&0&UID0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | None | None | None | (Standard monitor types) | Generic Non-PnP Monitor | 96 | 96 |
```
### CIM_DeviceAccessedByFile
### CIM_DeviceConnection
rpc上では実行できない
### CIM_DeviceErrorCounts
### CIM_DeviceFile
### CIM_DeviceSAPImplementation
### CIM_DeviceServiceImplementation
### CIM_DeviceSoftware
### CIM_Directory
```sh
WQL> SELECT * FROM CIM_Directory WHERE Caption = "C:\\"
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | 
| C:\ | C:\ | None | c:\ | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | True | CIM_LogicalFile | None | True | Win32_FileSystem | NTFS | None | None | True | 18446744073709551615 | True | True | True | Local Disk |  | None | None | c: |  |  |  | 18809343 |
```
### CIM_DirectoryAction
```sh
WQL> SELECT * FROM CIM_DirectoryAction
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | ActionID | Direction | Caption | Description | DirectoryName | 
| None | None | 65535 | None | 65535 | INSTALLDIR{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | INSTALLDIR | INSTALLDIR | INSTALLDIR | 
| None | None | 65535 | None | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | VMWARETOOLS_CMNAPPDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_SERVER.869A7E00_8665_0000_83A8_EF0F76CF0001 | 
| None | None | 65535 | None | 65535 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 | GUESTPROXYDATA_TRUSTED.869A7E00_8665_0000_83A8_EF0F76CF0001 |
```
### CIM_DirectoryContainsFile
```sh
WQL> SELECT * FROM CIM_DirectoryContainsFile WHERE GroupComponent = "Win32_Directory.Name='C:\\'"
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\bootmgr" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\BOOTNXT" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\pagefile.sys" |
```
### CIM_DirectorySpecification
省略
```sh
WQL> SELECT * FROM CIM_DirectorySpecification
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | CheckID | Description | Caption | CheckMode | DirectoryType | DirectoryPath | DefaultDir | Directory | 
| C_x86_Runtime_Detection | 14.12.25810 | 2 | {E3819B64-3C56-3DD7-921D-00B011AD31DE} | 19 | TARGETDIR{E3819B64-3C56-3DD7-921D-00B011AD31DE}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR | 
| Servicing_Key_ProductFamily_x86 | 14.12.25810 | 2 | {C96DC6F1-894A-33E0-A8C1-3E9E7394FA28} | 19 | TARGETDIR{C96DC6F1-894A-33E0-A8C1-3E9E7394FA28}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR | 
| Servicing_Key_ProductEdition_x86 | 14.12.25810 | 2 | {1EA220DF-5B36-3289-B979-D06841E41888} | 19 | TARGETDIR{1EA220DF-5B36-3289-B979-D06841E41888}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR |

~~~
```
### CIM_DirectorySpecificationFile
### CIM_DiscreteSensor
### CIM_DiskDrive 
```sh
WQL> SELECT * FROM CIM_DiskDrive 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Capabilities | CapabilityDescriptions | CompressionMethod | ErrorMethodology | MaxMediaSize | DefaultBlockSize | MaxBlockSize | MinBlockSize | NumberOfMediaSupported | NeedsCleaning | BytesPerSector | InterfaceType | Partitions | SectorsPerTrack | TotalCylinders | TotalHeads | TotalSectors | TotalTracks | TracksPerCylinder | Index | Manufacturer | MediaLoaded | MediaType | Model | SCSIBus | SCSILogicalUnit | SCSIPort | SCSITargetId | Size | Signature | SerialNumber | FirmwareRevision | 
| VMware Virtual disk SCSI Disk Device | Disk drive | None | \\.\PHYSICALDRIVE0 | OK | 65535 | Win32_DiskDrive | 0 | False | \\.\PHYSICALDRIVE0 | None | SCSI\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\5&1982005&0&000100 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 4  | 396 411  | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | None | True | 512 | SCSI | 3 | 63 | 2610 | 255 | 41929650 | 665550 | 255 | 0 | (Standard disk drives) | True | Fixed hard disk media | VMware Virtual disk SCSI Disk Device | 0 | 0 | 0 | 1 | 21467980800 | None | 6000c29c9f4f2e0c794e36b137fda25f | 2.0  |
```
### CIM_DisketteDrive 
### CIM_DiskPartition
```sh
WQL> SELECT * FROM CIM_DiskPartition
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | Bootable | PrimaryPartition | BootPartition | DiskIndex | HiddenSectors | Index | RewritePartition | Size | StartingOffset | Type | 
| Disk #0, Partition #0 | GPT: Unknown | None | Disk #0, Partition #0 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 921600 | None | False | False | False | 0 | None | 0 | None | 471859200 | 135266304 | GPT: Unknown | 
| Disk #0, Partition #1 | GPT: System | None | Disk #0, Partition #1 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 202752 | None | True | True | True | 0 | None | 1 | None | 103809024 | 607125504 | GPT: System | 
| Disk #0, Partition #2 | GPT: Basic Data | None | Disk #0, Partition #2 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #2 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 40552448 | None | False | True | False | 0 | None | 2 | None | 20762853376 | 710934528 | GPT: Basic Data | 
```
### CIM_DiskSpaceCheck
### CIM_Display 
```sh
WQL> SELECT * FROM CIM_Display 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | DisplayType | Bandwidth | ScreenHeight | ScreenWidth | MonitorManufacturer | MonitorType | PixelsPerXLogicalInch | PixelsPerYLogicalInch | 
| Generic Non-PnP Monitor | Generic Non-PnP Monitor | None | Generic Non-PnP Monitor | OK | 8 | Win32_DesktopMonitor | 0 | False | DesktopMonitor1 | None | DISPLAY\DEFAULT_MONITOR\4&31BE19FA&0&UID0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | None | None | None | (Standard monitor types) | Generic Non-PnP Monitor | 96 | 96 |
```
### CIM_DMA
```sh
WQL> SELECT * FROM CIM_DMA
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | DMAChannel | Availability | BurstMode | TransferWidths | AddressSize | MaxTransferSize | ByteMode | WordMode | ChannelTiming | TypeCTiming | Port | 
| Channel 4 | Channel 4 | None | Channel 4 | OK | Win32_ComputerSystem | FOREST | Win32_DMAChannel | 4 | 4 | True | 0  | 0 | 0 | 2 | 2 | 2 | 2 | None |
```
### CIM_Docked
### CIM_ElementCapacity
### CIM_ElementConfiguration
### CIM_ElementSetting 
```sh
WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "CIM_DataFile.Name='C:\\bootmgr'"
| Element | Setting | 
| CIM_DataFile.Name="C:\\bootmgr" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="C:\\bootmgr" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_ClassicCOMClass.ComponentId='{A2D75874-6750-4931-94C1-C99D3BC9D0C7}'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ClassicCOMClass.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" | \\FOREST\root\cimv2:Win32_ClassicCOMClassSetting.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_ComputerSystem.Name='FOREST'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_BootConfiguration.Name="BootConfiguration" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="NT AUTHORITY\\SYSTEM" | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_TimeZone.StandardName="Pacific Standard Time" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu" | 
~~~

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_DCOMApplication.AppID='{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_DCOMApplicationSetting.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | 

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_Directory.Name='C:\\'"
| Element | Setting | 
| Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="C:\\" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_NetworkAdapter.DeviceID='0'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=0 |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_OperatingSystem=@"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_OperatingSystem=@ | \\FOREST\root\cimv2:Win32_AutochkSetting.SettingID="Microsoft Windows Server 2016 Standard|C:\\Windows|\\Device\\Harddisk0\\Partition4" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_Service='winmgmt'"
| Element | Setting | 
| Win32_Service="winmgmt" | Win32_WMISetting=@ |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_UserAccount.Domain='htb',Name='administrator'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_UserAccount.Domain="HTB",Name="Administrator" | \\FOREST\root\cimv2:Win32_Desktop.Name="HTB\\Administrator" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_VideoController.DeviceID='*'"
| Element | Setting | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" | 
| Win32_VideoController.DeviceID="*" | \\FOREST\root\cimv2:Win32_LogicalFileSecuritySetting.Path="*" |

WQL> SELECT * FROM CIM_ElementSetting WHERE Element = "Win32_Volume.DeviceID='\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\'"
| Element | Setting | 
| Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | Win32_QuotaSetting.VolumePath="C:\\" | 
```
### CIM_ElementsLinked
### CIM_ErrorCountersForDevice
### CIM_ExecuteProgram 
### CIM_Export 
### CIM_ExtraCapacityGroup 
### CIM_Fan 
### CIM_FileAction
省略　　　
```sh
WQL> SELECT * FROM CIM_FileAction 
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | ActionID | Direction | Caption | Description | Source | Destination | DeleteAfterCopy | FileKey | 
| Driver_Audio.D549868E_41DC_43CB_8703_8CBB2211BAF6 | None | 65535 | None | 65535 | Driver_Audio.D549868E_41DC_43CB_8703_8CBB2211BAF6{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | Driver_Audio.D549868E_41DC_43CB_8703_8CBB2211BAF6 | Driver_Audio.D549868E_41DC_43CB_8703_8CBB2211BAF6 | None | *.* | DRIVER_AUDIO.D549868E_41DC_43CB_8703_8CBB2211BAF6 | Driver_Audio.D549868E_41DC_43CB_8703_8CBB2211BAF6 | 3 | 
| Driver_Audio_Vista.D549868E_41DC_43CB_8703_8CBB2211BAF6 | None | 65535 | None | 65535 | Driver_Audio_Vista.D549868E_41DC_43CB_8703_8CBB2211BAF6{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | Driver_Audio_Vista.D549868E_41DC_43CB_8703_8CBB2211BAF6 | Driver_Audio_Vista.D549868E_41DC_43CB_8703_8CBB2211BAF6 | None | *.* | DRIVER_AUDIO_COMPONENT_DIR.D549868E_41DC_43CB_8703_8CBB2211BAF6 | Driver_Audio_Vista.D549868E_41DC_43CB_8703_8CBB2211BAF6 | 3 | 
| Remove_vmacthlp.log.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2 | None | 65535 | None | 65535 | Remove_vmacthlp.log.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2{748D3A12-9B82-4B08-A0FF-CFDE83612E87} | 65535 | Remove_vmacthlp.log.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2 | Remove_vmacthlp.log.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2 | None | vmacthlp.log | INSTALLDIR.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2 | Remove_vmacthlp.log.9BE26984_A19E_412C_B1FB_B6BA1C8D2BE2 | 2 |

~~~
```
### CIM_FileSpecification
省略
```sh
WQL> SELECT * FROM CIM_FileSpecification  
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | CheckID | Description | Caption | CheckMode | CreateTimeStamp | FileSize | CheckSum | CRC1 | CRC2 | MD5Checksum | Language | Attributes | Sequence | FileID | 
| mfc140.dll_system_x86 | 14.12.25810 | 2 | {4FD4AB8C-C57F-3782-9230-9CCA22153AD3} | 19 | mfc140.dll{7FED75A1-600C-394B-8376-712E2A8861F2} | mfc140.dll | mfc140.dll | True | None | 4821632 | None | None | None | None | 1033 | 512 | 1 | None | 
| mfc140u.dll_system_x86 | 14.12.25810 | 2 | {46A1EA6B-3D81-3399-8991-127F7F7AE76A} | 19 | mfc140u.dll{7FED75A1-600C-394B-8376-712E2A8861F2} | mfc140u.dll | mfc140u.dll | True | None | 5124744 | None | None | None | None | 1033 | 512 | 12 | None | 
| mfcm140.dll_system_x86 | 14.12.25810 | 2 | {C94DDE19-CC70-3B9A-A6AF-5CA7340B9B9A} | 19 | mfcm140.dll{7FED75A1-600C-394B-8376-712E2A8861F2} | mfcm140.dll | mfcm140.dll | True | None | 92296 | None | None | None | None | 1033 | 512 | 13 | None |

~~~
```
### CIM_FileStorage 
### CIM_FileSystem 
### CIM_FlatPanel 
### CIM_FromDirectoryAction 
### CIM_HostedFileSystem 
### CIM_HostedJobDestination 
### CIM_HostedService 
### CIM_InfraredController 
### CIM_InstalledOS 
```sh
WQL> SELECT * FROM CIM_InstalledOS 
| GroupComponent | PartComponent | PrimaryOS | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_OperatingSystem=@ | True |
```
### CIM_InstalledSoftwareElement
省略
```sh
WQL> SELECT * FROM CIM_InstalledSoftwareElement 
| Software | System | 
| Win32_SoftwareElement.Name="C_x86_Runtime_Detection",SoftwareElementID="{E3819B64-3C56-3DD7-921D-00B011AD31DE}",SoftwareElementState=2,TargetOperatingSystem=19,Version="14.12.25810" | Win32_ComputerSystem.Name="FOREST" | 
| Win32_SoftwareElement.Name="mfc140.dll_system_x86",SoftwareElementID="{4FD4AB8C-C57F-3782-9230-9CCA22153AD3}",SoftwareElementState=2,TargetOperatingSystem=19,Version="14.12.25810" | Win32_ComputerSystem.Name="FOREST" | 
| Win32_SoftwareElement.Name="mfc140u.dll_system_x86",SoftwareElementID="{46A1EA6B-3D81-3399-8991-127F7F7AE76A}",SoftwareElementState=2,TargetOperatingSystem=19,Version="14.12.25810" | Win32_ComputerSystem.Name="FOREST" |

~~~
```
### CIM_IRQ
省略
```sh
WQL> SELECT * FROM CIM_IRQ
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | IRQNumber | Availability | TriggerType | TriggerLevel | Shareable | Vector | Hardware | 
| IRQ 4294967293 | IRQ 4294967293 | None | IRQ4294967293 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967293 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967292 | IRQ 4294967292 | None | IRQ4294967292 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967292 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967291 | IRQ 4294967291 | None | IRQ4294967291 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967291 | 2 | 2 | 2 | True | None | True |

~~~
```
### CIM_Job 
### CIM_JobDestination 
### CIM_JobDestinationJobs 
### CIM_Keyboard
```sh
WQL> SELECT * FROM CIM_Keyboard 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | Layout | NumberOfFunctionKeys | Password | 
| Enhanced (101- or 102-key) | Standard PS/2 Keyboard | None | Enhanced (101- or 102-key) | OK | 65535 | Win32_Keyboard | 0 | False | ACPI\PNP0303\4&25EE97C0&0 | None | ACPI\PNP0303\4&25EE97C0&0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 00000409 | 12 | 65535 |
```
### CIM_LinkHasConnector
### CIM_LocalFileSystem 
### CIM_Location 
### CIM_LogicalDevice
rpc上では実行できない
### CIM_LogicalDisk
```sh
WQL> SELECT * FROM CIM_LogicalDisk
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | FreeSpace | Size | Compressed | DriveType | FileSystem | MaximumComponentLength | ProviderName | SupportsFileBasedCompression | VolumeName | VolumeSerialNumber | MediaType | SupportsDiskQuotas | QuotasDisabled | QuotasIncomplete | QuotasRebuilding | VolumeDirty | 
| C: | Local Fixed Disk | None | C: | None | 65535 | Win32_LogicalDisk | None | True | C: | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 18446744073709551615 | None | 18446744073709551615 | None | 10410131456 | 20762849280 | False | 3 | NTFS | 255 | None | True |  | 61F2A88F | 12 | True | True | False | False | False |
```
### CIM_LogicalDiskBasedOnPartition
```sh
WQL> SELECT * FROM CIM_LogicalDiskBasedOnPartition
| Antecedent | Dependent | StartingAddress | EndingAddress | 
| \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" | \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | 710934528 | 21473787903 |
```
### CIM_LogicalDiskBasedOnVolumeSet
### CIM_LogicalElement 
```sh
WQL> SELECT * FROM CIM_LogicalFile WHERE Name = "C:\\"
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | 
| C:\ | C:\ | None | c:\ | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | True | CIM_LogicalFile | None | True | Win32_FileSystem | NTFS | None | None | True | 18446744073709551615 | True | True | True | Local Disk |  | None | None | c: |  |  |  | 18809343 |
```
### CIM_LogicalFile
```sh
WQL> SELECT * FROM CIM_LogicalFile WHERE Name = "C:\\"
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | 
| C:\ | C:\ | None | c:\ | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | True | CIM_LogicalFile | None | True | Win32_FileSystem | NTFS | None | None | True | 18446744073709551615 | True | True | True | Local Disk |  | None | None | c: |  |  |  | 18809343 |
```
### CIM_LogicalIdentity 
### CIM_MagnetoOpticalDrive 
### CIM_ManagedSystemElement  
rpc上では実行できない
### CIM_ManagementController 
### CIM_MediaAccessDevice
```sh
WQL> SELECT * FROM CIM_MediaAccessDevice 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Capabilities | CapabilityDescriptions | CompressionMethod | ErrorMethodology | MaxMediaSize | DefaultBlockSize | MaxBlockSize | MinBlockSize | NumberOfMediaSupported | NeedsCleaning | BytesPerSector | InterfaceType | Partitions | SectorsPerTrack | TotalCylinders | TotalHeads | TotalSectors | TotalTracks | TracksPerCylinder | Index | Manufacturer | MediaLoaded | MediaType | Model | SCSIBus | SCSILogicalUnit | SCSIPort | SCSITargetId | Size | Signature | SerialNumber | FirmwareRevision | 
| VMware Virtual disk SCSI Disk Device | Disk drive | None | \\.\PHYSICALDRIVE0 | OK | 65535 | Win32_DiskDrive | 0 | False | \\.\PHYSICALDRIVE0 | None | SCSI\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\5&1982005&0&000100 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 4  | 396 411  | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | None | True | 512 | SCSI | 3 | 63 | 2610 | 255 | 41929650 | 665550 | 255 | 0 | (Standard disk drives) | True | Fixed hard disk media | VMware Virtual disk SCSI Disk Device | 0 | 0 | 0 | 1 | 21467980800 | None | 6000c29c9f4f2e0c794e36b137fda25f | 2.0  |
```
### CIM_MediaPresent
```sh
WQL> SELECT * FROM CIM_MediaPresent 
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #0" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #1" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" | 
```
### CIM_Memory
```sh
WQL> SELECT * FROM CIM_Memory 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | Level | WritePolicy | CacheType | LineSize | ReplacementPolicy | ReadPolicy | FlushTimer | Associativity | Location | MaxCacheSize | InstalledSize | SupportedSRAM | CurrentSRAM | ErrorCorrectType | CacheSpeed | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 0 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 1 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 2 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 3 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 4 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 5 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None |
```
### CIM_MemoryCapacity 
### CIM_MemoryCheck 
### CIM_MemoryMappedIO
省略
```sh
WQL> SELECT * FROM CIM_MemoryMappedIO 
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | StartingAddress | EndingAddress | MemoryType | 
| 0xE0000000-0xE7FFFFFF | 0xE0000000-0xE7FFFFFF | None | 0xE0000000-0xE7FFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 3758096384 | 3892314111 | None | 
~~~
| 0x00000400-0x0000041F | 0x00000400-0x0000041F | None | 0x00000400-0x0000041F | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 1024 | 1055 | False | 
~~~
```








# Win32 Provider
## Computer System Hardware Classes
### Cooling Device Classes
#### Win32_Fan
#### Win32_HeatPipe
#### Win32_Refrigeration
#### Win32_TemperatureProbe


### Input Device Classes
#### Win32_Keyboard
```sh
WQL> SELECT * FROM Win32_Keyboard
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | Layout | NumberOfFunctionKeys | Password | 
| Enhanced (101- or 102-key) | Standard PS/2 Keyboard | None | Enhanced (101- or 102-key) | OK | 65535 | Win32_Keyboard | 0 | False | ACPI\PNP0303\4&25EE97C0&0 | None | ACPI\PNP0303\4&25EE97C0&0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 00000409 | 12 | 65535 |
```
#### Win32_PointingDevice
```sh 
WQL> SELECT * FROM Win32_PointingDevice
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | Handedness | NumberOfButtons | PointingType | Resolution | HardwareType | InfFileName | InfSection | SampleRate | Synch | DoubleSpeedThreshold | QuadSpeedThreshold | DeviceInterface | Manufacturer | 
| VMware Pointing Device | VMware Pointing Device | None | VMware Pointing Device | OK | 65535 | Win32_PointingDevice | 0 | False | ACPI\VMW0003\4&25EE97C0&0 | None | ACPI\VMW0003\4&25EE97C0&0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | 0 | 2 | None | VMware Pointing Device | oem5.inf | VMMouse | None | None | None | None | 1 | VMware, Inc. |
```


### Mass Storage Classes
#### Win32_AutochkSetting
```sh
WQL> SELECT * FROM Win32_AutochkSetting
| SettingID | Caption | Description | UserInputDelay | 
| Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | None | None | 10 |
```
#### Win32_CDROMDrive
#### Win32_DiskDrive
```sh
WQL> SELECT * FROM Win32_DiskDrive
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Capabilities | CapabilityDescriptions | CompressionMethod | ErrorMethodology | MaxMediaSize | DefaultBlockSize | MaxBlockSize | MinBlockSize | NumberOfMediaSupported | NeedsCleaning | BytesPerSector | InterfaceType | Partitions | SectorsPerTrack | TotalCylinders | TotalHeads | TotalSectors | TotalTracks | TracksPerCylinder | Index | Manufacturer | MediaLoaded | MediaType | Model | SCSIBus | SCSILogicalUnit | SCSIPort | SCSITargetId | Size | Signature | SerialNumber | FirmwareRevision | 
| VMware Virtual disk SCSI Disk Device | Disk drive | None | \\.\PHYSICALDRIVE0 | OK | 65535 | Win32_DiskDrive | 0 | False | \\.\PHYSICALDRIVE0 | None | SCSI\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\5&1982005&0&000100 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 4  | 396 411  | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | None | True | 512 | SCSI | 3 | 63 | 2610 | 255 | 41929650 | 665550 | 255 | 0 | (Standard disk drives) | True | Fixed hard disk media | VMware Virtual disk SCSI Disk Device | 0 | 0 | 0 | 1 | 21467980800 | None | 6000c29c9f4f2e0c794e36b137fda25f | 2.0  |
```
#### Win32_FloppyDrive
#### Win32_PhysicalMedia
```sh
WQL> SELECT * FROM Win32_PhysicalMedia
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Capacity | MediaType | MediaDescription | WriteProtectOn | CleanerMedia | 
| None | None | None | None | None | None | None | None | None | 6000c29c9f4f2e0c794e36b137fda25f | \\.\PHYSICALDRIVE0 | None | None | None | True | True | True | True | 18446744073709551615 | 65535 | None | True | True |
```
#### Win32_TapeDrive


### Motherboard, Controller, and Port Classes
#### Win32_1394Controller
#### Win32_1394ControllerDevice
#### Win32_AllocatedResource
#### Win32_AssociatedProcessorMemory
```sh
WQL> SELECT * FROM Win32_AssociatedProcessorMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None |
```
#### Win32_BaseBoard
```sh
WQL> SELECT * FROM Win32_BaseBoard
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | HostingBoard | SlotLayout | RequiresDaughterBoard | SpecialRequirements | RequirementsDescription | Product | ConfigOptions | 
| Base Board | Base Board | None | Base Board | OK | Win32_BaseBoard | Intel Corporation | None | None | None | Base Board | None | None | None | True | False | False | False | None | None | None | None | False | None | False | True | None | 440BX Desktop Reference Platform | None |
```
#### Win32_BIOS
```sh
WQL> SELECT * FROM Win32_BIOS
| Caption | Description | InstallDate | Name | Status | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | OtherTargetOS | Manufacturer | BuildNumber | SerialNumber | CodeSet | IdentificationCode | LanguageEdition | PrimaryBIOS | ReleaseDate | BiosCharacteristics | InstallableLanguages | ListOfLanguages | CurrentLanguage | SMBIOSPresent | SMBIOSMajorVersion | SMBIOSMinorVersion | SMBIOSBIOSVersion | BIOSVersion | SystemBiosMajorVersion | SystemBiosMinorVersion | EmbeddedControllerMajorVersion | EmbeddedControllerMinorVersion | 
| VMW71.00V.24504846.B64.2501180334 | VMW71.00V.24504846.B64.2501180334 | None | VMW71.00V.24504846.B64.2501180334 | OK | INTEL  - 6040000 | 3 | VMW71.00V.24504846.B64.2501180334 | 0 | None | VMware, Inc. | None | VMware-42 14 dd 01 77 df ed 36-48 41 b0 f9 f7 10 45 bd | None | None | None | True | 20250118000000.000000+000 | 4 7 9 11 42 43  | None | None | None | True | 2 | 7 | VMW71.00V.24504846.B64.2501180334 | INTEL  - 6040000 VMW71.00V.24504846.B64.2501180334 VMware, Inc. - 10000  | 255 | 255 | 255 | 255 |
```
#### Win32_Bus
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
#### Win32_CacheMemory
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
#### Win32_ControllerHasHub
#### Win32_DeviceBus
```sh
WQL> SELECT * FROM Win32_DeviceBus
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 

~~~
```
#### Win32_DeviceMemoryAddress
```sh
WQL> SELECT * FROM Win32_DeviceMemoryAddress
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | StartingAddress | EndingAddress | MemoryType | 
| 0xE0000000-0xE7FFFFFF | 0xE0000000-0xE7FFFFFF | None | 0xE0000000-0xE7FFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 3758096384 | 3892314111 | None | 
| 0xFFC00000-0xFFDFFFFF | 0xFFC00000-0xFFDFFFFF | None | 0xFFC00000-0xFFDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4290772992 | 4292870143 | None | 
| 0xFEA00000-0xFEAFFFFF | 0xFEA00000-0xFEAFFFFF | None | 0xFEA00000-0xFEAFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4271898624 | 4272947199 | WindowDecode | 

~~~
```
#### Win32_DeviceSettings
#### Win32_DMAChannel
```sh
WQL> SELECT * FROM Win32_DMAChannel
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | DMAChannel | Availability | BurstMode | TransferWidths | AddressSize | MaxTransferSize | ByteMode | WordMode | ChannelTiming | TypeCTiming | Port | 
| Channel 4 | Channel 4 | None | Channel 4 | OK | Win32_ComputerSystem | FOREST | Win32_DMAChannel | 4 | 4 | True | 0  | 0 | 0 | 2 | 2 | 2 | 2 | None |
```
#### Win32_FloppyController
#### Win32_IDEController
```sh
WQL> SELECT * FROM Win32_IDEController
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | MaxNumberControlled | ProtocolSupported | TimeOfLastReset | Manufacturer | 
| ATA Channel 0 | IDE Channel | None | ATA Channel 0 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| ATA Channel 1 | IDE Channel | None | ATA Channel 1 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| Standard SATA AHCI Controller | Standard SATA AHCI Controller | None | Standard SATA AHCI Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | None | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Standard SATA AHCI Controller | 
| Intel(R) 82371AB/EB PCI Bus Master IDE Controller | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | None | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | None | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Intel |
```
#### Win32_IDEControllerDevice
```sh
WQL> SELECT * FROM Win32_IDEControllerDevice
| Antecedent | Dependent | NegotiatedSpeed | NegotiatedDataWidth | AccessState | NumberOfHardResets | NumberOfSoftResets | 
| \\FOREST\root\cimv2:Win32_IDEController.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | 18446744073709551615 | None | 65535 | None | None | 
| \\FOREST\root\cimv2:Win32_IDEController.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | 18446744073709551615 | None | 65535 | None | None |
```
#### Win32_InfraredDevice
#### Win32_IRQResource
```sh
WQL> SELECT * FROM Win32_IRQResource
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | IRQNumber | Availability | TriggerType | TriggerLevel | Shareable | Vector | Hardware | 
| IRQ 4294967293 | IRQ 4294967293 | None | IRQ4294967293 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967293 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967292 | IRQ 4294967292 | None | IRQ4294967292 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967292 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967291 | IRQ 4294967291 | None | IRQ4294967291 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967291 | 2 | 2 | 2 | True | None | True | 

~~~
```
#### Win32_MemoryArray
```sh
WQL> SELECT * FROM Win32_MemoryArray 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | ErrorGranularity | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None |
```
#### Win32_MemoryArrayLocation
```sh
WQL> SELECT * FROM Win32_MemoryArrayLocation
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 0" | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 1" |
```
#### Win32_MemoryDevice
```sh
WQL> SELECT * FROM Win32_MemoryDevice
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | ErrorGranularity | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None |
```
#### Win32_MemoryDeviceArray
```sh
WQL> SELECT * FROM Win32_MemoryDeviceArray
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 0" | 
| \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 1" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 1" |
```
#### Win32_MemoryDeviceLocation
```sh
WQL> SELECT * FROM Win32_MemoryDeviceLocation
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 0" | 
| \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 1" |
```
#### Win32_MotherboardDevice
```sh
WQL> SELECT * FROM Win32_MotherboardDevice
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | PrimaryBusType | RevisionNumber | SecondaryBusType | 
| Motherboard | Motherboard | None | Motherboard | OK | 3 | Win32_MotherBoardDevice | None | True | Motherboard | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | PCI | None | ISA |
```
#### Win32_OnBoardDevice
```sh
WQL> SELECT * FROM Win32_OnBoardDevice
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | DeviceType | Enabled | 
| On Board Device | VMware SVGA II | None | On Board Device | None | Win32_OnBoardDevice | None | None | None | None | On Board Device 0 | None | None | None | True | True | True | True | 3 | False | 
| On Board Device | ES1371 | None | On Board Device | None | Win32_OnBoardDevice | None | None | None | None | On Board Device 1 | None | None | None | True | True | True | True | 7 | False |
```
#### Win32_ParallelPort
#### Win32_PCMCIAController
#### Win32_PhysicalMemory
```sh
WQL> SELECT * FROM Win32_PhysicalMemory 
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | FormFactor | MemoryType | TotalWidth | DataWidth | Speed | Capacity | BankLabel | PositionInRow | InterleavePosition | DeviceLocator | TypeDetail | InterleaveDataDepth | Attributes | ConfiguredClockSpeed | MinVoltage | MaxVoltage | ConfiguredVoltage | SMBIOSMemoryType | 
| Physical Memory | Physical Memory | None | Physical Memory | None | Win32_PhysicalMemory | VMware Virtual RAM | None | None | 00000001 | Physical Memory 0 | None | VMW-2048MB | None | True | True | True | True | 8 | 2 | 64 | 64 | None | 2147483648 | RAM slot #0 | None | None | RAM slot #0 | 128 | None | 0 | 4800 | None | None | None | 3 |
```
#### Win32_PhysicalMemoryArray
```sh
WQL> SELECT * FROM Win32_PhysicalMemoryArray
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | Location | Use | MemoryErrorCorrection | MaxCapacity | MaxCapacityEx | MemoryDevices | 
| Physical Memory Array | Physical Memory Array | None | Physical Memory Array | None | Win32_PhysicalMemoryArray | None | None | None | None | Physical Memory Array 0 | None | None | None | True | True | True | True | None | None | None | None | 3 | 3 | 3 | 2097152 | 2097152 | 64 |
```
#### Win32_PhysicalMemoryLocation
```sh
WQL> SELECT * FROM Win32_PhysicalMemoryLocation
| GroupComponent | PartComponent | LocationWithinContainer | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | None |
```
#### Win32_PnPAllocatedResource
```sh
WQL> SELECT * FROM Win32_PnPAllocatedResource
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3758096384" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1024" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4290772992" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 

~~~
```
#### Win32_PNPDevice
#### Win32_PnPEntity
```sh
WQL> SELECT * FROM Win32_PnPEntity
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | HardwareID | CompatibleID | Manufacturer | Service | PNPClass | ClassGuid | Present | 
| Motherboard resources | Motherboard resources | None | Motherboard resources | OK | 65535 | Win32_PnPEntity | 0 | False | ACPI\PNP0C02\4 | None | ACPI\PNP0C02\4 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | ACPI\VEN_PNP&DEV_0C02 ACPI\PNP0C02 *PNP0C02  | None | (Standard system devices) | None | System | {4d36e97d-e325-11ce-bfc1-08002be10318} | True | 
| Microsoft AC Adapter | Microsoft AC Adapter | None | Microsoft AC Adapter | OK | 65535 | Win32_PnPEntity | 0 | False | ACPI\ACPI0003\1 | None | ACPI\ACPI0003\1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | ACPI\VEN_ACPI&DEV_0003 ACPI\ACPI0003 *ACPI0003  | None | Microsoft | CmBatt | Battery | {72631e54-78a4-11d0-bcf7-00aa00b7b32a} | True | 
| PCI Express Root Port | PCI Express Root Port | None | PCI Express Root Port | OK | 65535 | Win32_PnPEntity | 0 | False | PCI\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\3&18D45AA6&0&A8 | None | PCI\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\3&18D45AA6&0&A8 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | PCI\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01 PCI\VEN_15AD&DEV_07A0&SUBSYS_07A015AD PCI\VEN_15AD&DEV_07A0&CC_060400 PCI\VEN_15AD&DEV_07A0&CC_0604  | PCI\VEN_15AD&DEV_07A0&REV_01 PCI\VEN_15AD&DEV_07A0 PCI\VEN_15AD&CC_060400 PCI\VEN_15AD&CC_0604 PCI\VEN_15AD PCI\CC_060400&DT_4 PCI\CC_060400 PCI\CC_0604&DT_4 PCI\CC_0604  | (Standard system devices) | pci | System | {4d36e97d-e325-11ce-bfc1-08002be10318} | True | 

~~~
```
#### Win32_PortConnector
```sh
WQL> SELECT * FROM Win32_PortConnector
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | ConnectorPinout | ConnectorType | InternalReferenceDesignator | ExternalReferenceDesignator | PortType | 
| Port Connector | Port Connector | None | Port Connector | None | Win32_PortConnector | None | None | None | None | Port Connector 0 | None | None | None | True | None | 21 2 90  | J19 | COM 1 | 9 | 
| Port Connector | Port Connector | None | Port Connector | None | Win32_PortConnector | None | None | None | None | Port Connector 1 | None | None | None | True | None | 23 3 91  | J23 | Parallel | 5 | 
| Port Connector | Port Connector | None | Port Connector | None | Win32_PortConnector | None | None | None | None | Port Connector 2 | None | None | None | True | None | 59 2  | J11 | Keyboard | 13 | 
| Port Connector | Port Connector | None | Port Connector | None | Win32_PortConnector | None | None | None | None | Port Connector 3 | None | None | None | True | None | 59 2  | J12 | PS/2 Mouse | 13 |
```
#### Win32_PortResource
```sh
WQL> SELECT * FROM Win32_PortResource
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | StartingAddress | EndingAddress | Alias | 
| 0x00000400-0x0000041F | 0x00000400-0x0000041F | None | 0x00000400-0x0000041F | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 1024 | 1055 | False | 
| 0x00004000-0x00004FFF | 0x00004000-0x00004FFF | None | 0x00004000-0x00004FFF | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 16384 | 20479 | False | 
| 0x00003000-0x00003FFF | 0x00003000-0x00003FFF | None | 0x00003000-0x00003FFF | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 12288 | 16383 | False | 

~~~
```
#### Win32_Processor
```sh
WQL> SELECT * FROM Win32_Processor
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | AddressWidth | CurrentClockSpeed | DataWidth | Family | OtherFamilyDescription | LoadPercentage | MaxClockSpeed | Role | UpgradeMethod | Stepping | UniqueId | Version | Manufacturer | L2CacheSize | L2CacheSpeed | L3CacheSize | L3CacheSpeed | Architecture | Level | Revision | CpuStatus | CurrentVoltage | ExtClock | ProcessorId | ProcessorType | NumberOfLogicalProcessors | NumberOfCores | SocketDesignation | VoltageCaps | VMMonitorModeExtensions | SecondLevelAddressTranslationExtensions | VirtualizationFirmwareEnabled | SerialNumber | AssetTag | PartNumber | NumberOfEnabledCore | ThreadCount | Characteristics | 
| AMD64 Family 25 Model 1 Stepping 1 | AMD64 Family 25 Model 1 Stepping 1 | None | AMD EPYC 7513 32-Core Processor                 | OK | 3 | Win32_Processor | None | True | CPU0 | None | None | False | 3 | Win32_ComputerSystem | FOREST | None | None | True | 64 | 2595 | 64 | 2 | None | 34 | 2595 | CPU | 4 | 1 | None | Model 1, Stepping 1 | AuthenticAMD | 512 | None | 32768 | 0 | 9 | 25 | 257 | 1 | 33 | None | 178BFBFF00A00F11 | 3 | 2 | 2 | CPU 0 | 2 | False | False | True |  |  |  | 2 | 0 | 44 |
```
#### Win32_SCSIController
```sh
WQL> SELECT * FROM Win32_SCSIController
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | MaxNumberControlled | ProtocolSupported | TimeOfLastReset | ControllerTimeouts | MaxDataWidth | MaxTransferRate | ProtectionManagement | Index | DriverName | DeviceMap | HardwareVersion | Manufacturer | 
| Microsoft Storage Spaces Controller | Microsoft Storage Spaces Controller | None | Microsoft Storage Spaces Controller | OK | 3 | Win32_SCSIController | 0 | False | ROOT\SPACEPORT\0000 | None | ROOT\SPACEPORT\0000 | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | None | 2 | None | None | None | 18446744073709551615 | 65535 | None | spaceport | None | None | Microsoft | 
| LSI Adapter, SAS 3000 series, 8-port with 1068 | LSI Adapter, SAS 3000 series, 8-port with 1068 | None | LSI Adapter, SAS 3000 series, 8-port with 1068 | OK | 3 | Win32_SCSIController | 0 | False | PCI\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\4&2732702B&0&00A8 | None | PCI\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\4&2732702B&0&00A8 | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | None | 2 | None | None | None | 18446744073709551615 | 65535 | None | LSI_SAS | None | None | LSI |
```
#### Win32_SCSIControllerDevice
```sh
WQL> SELECT * FROM Win32_SCSIControllerDevice
| Antecedent | Dependent | NegotiatedSpeed | NegotiatedDataWidth | AccessState | NumberOfHardResets | NumberOfSoftResets | 
| \\FOREST\root\cimv2:Win32_SCSIController.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SCSI\\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\\5&1982005&0&000100" | 18446744073709551615 | None | 65535 | None | None |
```
#### Win32_SerialPort
#### Win32_SerialPortConfiguration
#### Win32_SerialPortSetting
#### Win32_SMBIOSMemory
```sh
WQL> SELECT * FROM Win32_SMBIOSMemory
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | ErrorGranularity | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None |
```
#### Win32_SoundDevice
#### Win32_SystemBIOS
```sh
WQL> SELECT * FROM Win32_SystemBIOS
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_BIOS.Name="VMW71.00V.24504846.B64.2501180334",SoftwareElementID="VMW71.00V.24504846.B64.2501180334",SoftwareElementState=3,TargetOperatingSystem=0,Version="INTEL  - 6040000" |
```
#### Win32_SystemDriverPNPEntity
```sh
WQL> SELECT * FROM Win32_SystemDriverPNPEntity
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="CmBatt" | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="pci" | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="pci" | 

~~~
```
#### Win32_SystemEnclosure
```sh
WQL> SELECT * FROM Win32_SystemEnclosure
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | CableManagementStrategy | ServicePhilosophy | ServiceDescriptions | LockPresent | AudibleAlarm | VisibleAlarm | SecurityBreach | BreachDescription | NumberOfPowerCords | CurrentRequiredOrProduced | HeatGeneration | ChassisTypes | TypeDescriptions | SMBIOSAssetTag | SecurityStatus | 
| System Enclosure | System Enclosure | None | System Enclosure | None | Win32_SystemEnclosure | No Enclosure | None | None | None | System Enclosure 0 | N/A | None | None | True | True | True | True | None | None | None | None | None | None | None | False | True | True | 65535 | None | 65535 | None | 65535 | 1  | None | No Asset Tag | 3 |
```
#### Win32_SystemMemoryResource
```sh
WQL> SELECT * FROM Win32_SystemMemoryResource
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | StartingAddress | EndingAddress | Alias | 
| 0x00000400-0x0000041F | 0x00000400-0x0000041F | None | 0x00000400-0x0000041F | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 1024 | 1055 | False | 
| 0x00004000-0x00004FFF | 0x00004000-0x00004FFF | None | 0x00004000-0x00004FFF | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 16384 | 20479 | False | 
| 0x00003000-0x00003FFF | 0x00003000-0x00003FFF | None | 0x00003000-0x00003FFF | OK | Win32_ComputerSystem | FOREST | Win32_PortResource | 12288 | 16383 | False | 

~~~
```
#### Win32_SystemSlot
```sh
WQL> SELECT * FROM Win32_SystemSlot
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | ConnectorPinout | ConnectorType | SupportsHotPlug | HeightAllowed | LengthAllowed | MaxDataWidth | VccMixedVoltageSupport | VppMixedVoltageSupport | ThermalRating | SpecialPurpose | PurposeDescription | Number | SlotDesignation | CurrentUsage | PMESignal | Shared | SegmentGroupNumber | BusNumber | DeviceNumber | FunctionNumber | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 0 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 1 | PCI Slot J11 | 4 | False | False | 0 | 30720 | 80 | 0 | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 1 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 2 | PCI Slot J12 | 3 | False | False | 0 | 32768 | 80 | 0 | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 2 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 3 | PCI Slot J13 | 4 | False | False | 0 | 34816 | 80 | 0 | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 3 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 4 | PCI Slot J14 | 3 | False | False | 0 | 36864 | 80 | 0 | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 4 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 5 | PCI Slot J15 | 3 | False | False | 0 | 38912 | 80 | 0 | 
| System Slot | System Slot | None | System Slot | OK | Win32_SystemSlot | None | None | None | None | System Slot 5 | None | None | None | True | None | 43  | False | None | None | 2 | 3 2  | None | None | True | None | 6 | PCI Slot J16 | 3 | False | False | 0 | 40960 | 80 | 0 |
```
#### Win32_USBController
#### Win32_USBControllerDevice
#### Win32_USBHub


### Networking Device Classes
#### Win32_NetworkAdapter
```sh
WQL> SELECT * FROM Win32_NetworkAdapter
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | PermanentAddress | NetworkAddresses | Speed | MaxSpeed | AutoSense | ProductName | AdapterType | AdapterTypeId | MACAddress | ServiceName | Manufacturer | Installed | Index | InterfaceIndex | MaxNumberControlled | TimeOfLastReset | NetConnectionID | NetConnectionStatus | NetEnabled | GUID | PhysicalAdapter | 
| [00000000] Microsoft Kernel Debug Network Adapter | Microsoft Kernel Debug Network Adapter | None | Microsoft Kernel Debug Network Adapter | None | 3 | Win32_NetworkAdapter | 0 | False | 0 | None | ROOT\KDNIC\0000 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 18446744073709551615 | 18446744073709551615 | True | Microsoft Kernel Debug Network Adapter | None | None | None | kdnic | Microsoft | True | 0 | 3 | 0 | 20250901054812.493853-420 | None | None | None | None | False | 
| [00000001] Intel(R) 82574L Gigabit Network Connection | Intel(R) 82574L Gigabit Network Connection | None | Intel(R) 82574L Gigabit Network Connection | None | 3 | Win32_NetworkAdapter | 0 | False | 1 | None | PCI\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\005056FFFFB441AF00 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 1000000000 | 18446744073709551615 | True | Intel(R) 82574L Gigabit Network Connection | Ethernet 802.3 | 0 | 00:50:56:94:6B:77 | e1iexpress | Intel Corporation | True | 1 | 5 | 0 | 20250901054812.493853-420 | Ethernet0 | 2 | True | {E00B7E21-EE8E-4210-8C23-A108EFC92167} | True | 
| [00000002] Microsoft ISATAP Adapter | Microsoft ISATAP Adapter | None | Microsoft ISATAP Adapter | None | 3 | Win32_NetworkAdapter | 0 | False | 2 | None | SWD\IP_TUNNEL_VBUS\ISATAP_0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 100000 | 18446744073709551615 | True | Microsoft ISATAP Adapter | Tunnel | 15 | None | tunnel | Microsoft | True | 2 | 2 | 0 | 20250901054812.493853-420 | None | None | None | None | False | 
| [00000003] Microsoft Teredo Tunneling Adapter | Microsoft Teredo Tunneling Adapter | None | Microsoft Teredo Tunneling Adapter | None | 3 | Win32_NetworkAdapter | None | True | 3 | None | None | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 18446744073709551615 | 18446744073709551615 | True | Microsoft Teredo Tunneling Adapter | None | None | None | None | None | True | 3 | 4 | 0 | 20250901054812.493853-420 | None | None | None | None | False |
```
#### Win32_NetworkAdapterConfiguration
```sh
WQL> SELECT * FROM Win32_NetworkAdapterConfiguration
| SettingID | Caption | Description | GatewayCostMetric | DefaultIPGateway | DHCPEnabled | DHCPLeaseExpires | DHCPLeaseObtained | DHCPServer | Index | InterfaceIndex | IPAddress | IPSubnet | IPXAddress | MACAddress | ServiceName | IPEnabled | IPXEnabled | FullDNSRegistrationEnabled | DomainDNSRegistrationEnabled | IPConnectionMetric | DatabasePath | IPUseZeroBroadcast | ArpAlwaysSourceRoute | ArpUseEtherSNAP | DefaultTOS | DefaultTTL | DeadGWDetectEnabled | PMTUBHDetectEnabled | PMTUDiscoveryEnabled | ForwardBufferMemory | IGMPLevel | KeepAliveInterval | KeepAliveTime | MTU | NumForwardPackets | TcpMaxConnectRetransmissions | TcpMaxDataRetransmissions | TcpNumConnections | TcpUseRFC1122UrgentPointer | TcpWindowSize | IPPortSecurityEnabled | IPFilterSecurityEnabled | IPSecPermitTCPPorts | IPSecPermitUDPPorts | IPSecPermitIPProtocols | DNSHostName | DNSDomain | DNSServerSearchOrder | DNSDomainSuffixSearchOrder | DNSEnabledForWINSResolution | WINSEnableLMHostsLookup | WINSPrimaryServer | WINSSecondaryServer | WINSHostLookupFile | WINSScopeID | TcpipNetbiosOptions | IPXVirtualNetNumber | IPXNetworkNumber | IPXFrameType | IPXMediaType | 
| {D0F94394-DA53-47DE-9E02-938AF0CCD55D} | [00000000] Microsoft Kernel Debug Network Adapter | Microsoft Kernel Debug Network Adapter | None | None | True | None | None | None | 0 | 3 | None | None | None | None | kdnic | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| {E00B7E21-EE8E-4210-8C23-A108EFC92167} | [00000001] Intel(R) 82574L Gigabit Network Connection | Intel(R) 82574L Gigabit Network Connection | 0 256  | 10.129.0.1 fe80::250:56ff:feb9:f8ec  | True | 20250902094839.000000-420 | 20250902084839.000000-420 | 10.129.0.1 | 1 | 5 | 10.129.138.203 fe80::f078:8d45:3c85:5444 dead:beef::f078:8d45:3c85:5444 dead:beef::8e  | 255.255.0.0 64 64 128  | None | 00:50:56:94:6B:77 | e1iexpress | True | None | True | False | 25 | %SystemRoot%\System32\drivers\etc | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | False |  |  |  | FOREST | .htb | 127.0.0.1  | htb.local htb  | False | True | None | None | None |  | 0 | None | None | None | None | 
| {96B97A16-1CCD-406C-818E-52A0AE4FF243} | [00000002] Microsoft ISATAP Adapter | Microsoft ISATAP Adapter | None | None | False | None | None | None | 2 | 2 | None | None | None | None | tunnel | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| {D237B365-0ADE-4882-8122-5B874800EF32} | [00000003] Microsoft Teredo Tunneling Adapter | Microsoft Teredo Tunneling Adapter | None | None | False | None | None | None | 3 | 4 | None | None | None | None | tunnel | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None |
```
#### Win32_NetworkAdapterSetting
```sh
WQL> SELECT * FROM Win32_NetworkAdapterSetting
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=0 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=1 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="2" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=2 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="3" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=3 |
```


### Power Classes
#### Win32_Battery
#### Win32_CurrentProbe
#### Win32_PortableBattery
#### Win32_PowerManagementEvent
#### Win32_VoltageProbe


### Printing Classes
#### Win32_DriverForDevice
#### Win32_Printer
#### Win32_PrinterConfiguration
#### Win32_PrinterController
#### Win32_PrinterDriver
#### Win32_PrinterDriverDll
#### Win32_PrinterSetting
#### Win32_PrintJob
#### Win32_TCPIPPrinterPort


### Telephony Classes
#### Win32_POTSModem
#### Win32_POTSModemToSerialPort	


### Video and Monitor Classes
#### Win32_DesktopMonitor
```sh
WQL> SELECT * FROM Win32_DesktopMonitor
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | DisplayType | Bandwidth | ScreenHeight | ScreenWidth | MonitorManufacturer | MonitorType | PixelsPerXLogicalInch | PixelsPerYLogicalInch | 
| Generic Non-PnP Monitor | Generic Non-PnP Monitor | None | Generic Non-PnP Monitor | OK | 8 | Win32_DesktopMonitor | 0 | False | DesktopMonitor1 | None | DISPLAY\DEFAULT_MONITOR\4&31BE19FA&0&UID0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | None | None | None | (Standard monitor types) | Generic Non-PnP Monitor | 96 | 96 |
```
#### Win32_DisplayControllerConfiguration
```sh
WQL> SELECT * FROM Win32_DisplayControllerConfiguration
| SettingID | Caption | Description | BitsPerPixel | ColorPlanes | DeviceEntriesInAColorTable | DeviceSpecificPens | HorizontalResolution | Name | RefreshRate | ReservedSystemPaletteEntries | SystemPaletteEntries | VerticalResolution | VideoMode | 
| VMware SVGA 3D | VMware SVGA 3D | VMware SVGA 3D | 32 | 1 | None | None | 1024 | VMware SVGA 3D | 60 | None | None | 768 | 1024 by 768 pixels, True Color, 60 Hertz |
```
#### Win32_VideoController
```sh
WQL> SELECT * FROM Win32_VideoController
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | MaxNumberControlled | ProtocolSupported | TimeOfLastReset | VideoProcessor | VideoMemoryType | NumberOfVideoPages | MaxMemorySupported | AcceleratorCapabilities | CapabilityDescriptions | CurrentBitsPerPixel | CurrentHorizontalResolution | CurrentVerticalResolution | MaxRefreshRate | MinRefreshRate | CurrentRefreshRate | CurrentScanMode | CurrentNumberOfColors | CurrentNumberOfRows | CurrentNumberOfColumns | VideoArchitecture | VideoMode | NumberOfColorPlanes | AdapterCompatibility | AdapterDACType | AdapterRAM | Monochrome | DitherType | InfFilename | InfSection | InstalledDisplayDrivers | DriverDate | DriverVersion | ICMIntent | ICMMethod | SpecificationVersion | ColorTableEntries | DeviceSpecificPens | ReservedSystemPaletteEntries | SystemPaletteEntries | VideoModeDescription | 
| VMware SVGA 3D | VMware SVGA 3D | None | VMware SVGA 3D | OK | 3 | Win32_VideoController | 0 | False | VideoController1 | None | PCI\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\3&18D45AA6&0&78 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 65535 | None | VMware Virtual SVGA 3D Graphics Adapter | 2 | None | None | None | None | 32 | 1440 | 621 | 64 | 64 | 1 | 4 | 4294967296 | 0 | 0 | 5 | 65535 | 65535 | VMware, Inc. | n/a | 0 | False | 0 | oem6.inf | VM3D_AMD64 | vm3dum64_loader.dll,vm3dum64_loader.dll,vm3dum64_loader.dll,vm3dum_loader,vm3dum_loader,vm3dum_loader | 20180726000000.000000-000 | 8.16.1.1 | None | None | None | None | None | None | None | 1440 x 621 x 4294967296 colors | 
```
#### Win32_VideoSettings





## Operating System Classes
### COM
#### Win32_ClassicCOMClass
```sh
WQL> SELECT * FROM Win32_ClassicCOMClass WHERE Caption = "Microsoft Windows Defender"
| Caption | Description | InstallDate | Name | Status | ComponentId | 
| Microsoft Windows Defender | Microsoft Windows Defender | None | Microsoft Windows Defender | None | {A2D75874-6750-4931-94C1-C99D3BC9D0C7} | 
```
#### Win32_ClassicCOMClassSettings
```sh
WQL> SELECT * FROM Win32_ClassicCOMClassSettings WHERE Element = "Win32_ClassicCOMClass.ComponentId=\"{A2D75874-6750-4931-94C1-C99D3BC9D0C7}\""
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ClassicCOMClass.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" | \\FOREST\root\cimv2:Win32_ClassicCOMClassSetting.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" | 
```
#### Win32_ClassicCOMApplicationClasses
```sh
WQL> SELECT * FROM Win32_ClassicCOMApplicationClasses WHERE PartComponent = "Win32_ClassicCOMClass.ComponentId=\"{A2D75874-6750-4931-94C1-C99D3BC9D0C7}\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_ClassicComClass.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" | 
```
#### Win32_ClientApplicationSetting
#### Win32_COMApplication
```sh
WQL> SELECT * FROM Win32_COMApplication
| Caption | Description | InstallDate | Name | Status | AppID | 
| None | None | None | None | None | {00021401-0000-0000-C000-000000000046} | 
| None | None | None | None | None | {000C101C-0000-0000-C000-000000000046} | 
| User Notification | User Notification | None | User Notification | None | {0010890e-8789-413c-adbc-48f5b511b3af} | 
| DFSRHelper.ServerHealthReport Class | DFSRHelper.ServerHealthReport Class | None | DFSRHelper.ServerHealthReport Class | None | {01D0824E-81A6-447B-9223-167C2A78AFC8} | 
| PLA | PLA | None | PLA | None | {03837503-098b-11d8-9414-505054503030} | 
| COpenControlPanel | COpenControlPanel | None | COpenControlPanel | None | {06622D85-6856-4460-8DE1-A81921B41C4B} | 
| sppui | sppui | None | sppui | None | {0868DC9B-D9A2-4f64-9362-133CEA201299} | 
| PersistentZoneIdentifier | PersistentZoneIdentifier | None | PersistentZoneIdentifier | None | {0968e258-16c7-4dba-aa86-462dd61e31a3} | 
| None | None | None | None | None | {0A886F29-465A-4aea-8B8E-BE926BFAE83E} | 
| None | None | None | None | None | {0CA545C6-37AD-4A6C-BF92-9F7610067EF5} | 
| VCBSnapshotProvider | VCBSnapshotProvider | None | VCBSnapshotProvider | None | {13390438-AA43-44B5-AEF0-DA857DD05B00} | 
| Shell Create Object Task Server | Shell Create Object Task Server | None | Shell Create Object Task Server | None | {133eac4f-5891-4d04-bada-d84870380a80} | 
| Shell Create Object Handler | Shell Create Object Handler | None | Shell Create Object Handler | None | {135fd325-45b7-4c30-89f8-4386961669f0} | 
| None | None | None | None | None | {19BCA967-D266-436f-B2D4-CBE4D4B42F96} | 
| None | None | None | None | None | {1BE1F766-5536-11D1-B726-00C04FB926AF} | 
| %systemroot%\system32\lpksetup.exe | %systemroot%\system32\lpksetup.exe | None | %systemroot%\system32\lpksetup.exe | None | {1C749B87-568C-4865-8E73-6413F8372CE6} | 
| ThirdPartyEapDispatcherPeerConfig | ThirdPartyEapDispatcherPeerConfig | None | ThirdPartyEapDispatcherPeerConfig | None | {1F7D1BE9-7A50-40B6-A605-C4F3696F49C0} | 
| Microsoft WMI Provider Subsystem Secured Host | Microsoft WMI Provider Subsystem Secured Host | None | Microsoft WMI Provider Subsystem Secured Host | None | {1F87137D-0E7C-44d5-8C73-4EFFB68962F2} | 
| ThirdPartyEapDispatcherAuthenticatorConfig | ThirdPartyEapDispatcherAuthenticatorConfig | None | ThirdPartyEapDispatcherAuthenticatorConfig | None | {1FF84C3B-1140-4EB6-BE38-4BE618D2E7D6} | 
| Microsoft Software Protection Platform Admin Object (Inner) | Microsoft Software Protection Platform Admin Object (Inner) | None | Microsoft Software Protection Platform Admin Object (Inner) | None | {205609B7-5E08-443E-B0A7-A7AED3F3A717} | 
| Microsoft Windows WSMan Provider Host With User Settings | Microsoft Windows WSMan Provider Host With User Settings | None | Microsoft Windows WSMan Provider Host With User Settings | None | {209444d2-2540-495e-962c-a61ad3243526} | 
| MSDAINITIALIZE | MSDAINITIALIZE | None | MSDAINITIALIZE | None | {2206CDB0-19C1-11D1-89E0-00C04FD7A829} | 
| components | components | None | components | None | {259FD5A7-B58E-4160-A698-0348A02CA8E3} | 
| Microsoft WBEM Active Scripting Event Consumer Provider | Microsoft WBEM Active Scripting Event Consumer Provider | None | Microsoft WBEM Active Scripting Event Consumer Provider | None | {266C72E7-62E8-11D1-AD89-00C04FD8FDFF} | 
| WInRTDesktopBroker | WInRTDesktopBroker | None | WInRTDesktopBroker | None | {27550CA0-E9DE-4186-A566-37A59BB6CA69} | 
| None | None | None | None | None | {2781761E-28E2-4109-99FE-B9D127C57AFE} | 
| faultrep.dll | faultrep.dll | None | faultrep.dll | None | {2C256447-3F0D-4CBB-9D12-575BB20CDA0A} | 
| None | None | None | None | None | {2C5BC43E-3369-4C33-AB0C-BE9469677AF4} | 
| None | None | None | None | None | {304CE942-6E39-40D8-943A-B913C40C9CD4} | 
| DFSRHelper.ADProxy Class | DFSRHelper.ADProxy Class | None | DFSRHelper.ADProxy Class | None | {33024A8D-6A46-4acd-95B3-9D9EBBEAD458} | 
| DFSRHelper.ServerHealthReport Class | DFSRHelper.ServerHealthReport Class | None | DFSRHelper.ServerHealthReport Class | None | {36C95A5F-0A17-47c7-9983-F6BFD009A867} | 
| None | None | None | None | None | {3ad05575-8857-4850-9277-11b85bdb8e09} | 
| Microsoft Windows Remote Shell Host | Microsoft Windows Remote Shell Host | None | Microsoft Windows Remote Shell Host | None | {3e5ca495-8d6a-4d1f-ad99-177b426c8b8e} | 
| WinInetCacheServer | WinInetCacheServer | None | WinInetCacheServer | None | {3eb3c877-1f16-487c-9050-104dbcd66683} | 
| None | None | None | None | None | {3eef301f-b596-4c0b-bd92-013beafce793} | 
| Microsoft Windows WSMan Provider Host | Microsoft Windows WSMan Provider Host | None | Microsoft Windows WSMan Provider Host | None | {3feb2f63-0eec-4b96-84ab-da1307e0117c} | 
| None | None | None | None | None | {42CBFAA7-A4A7-47BB-B422-BD10E9D02700} | 
| SPP External COM Object | SPP External COM Object | None | SPP External COM Object | None | {44831FEC-DC51-4716-A7E1-E898FDF83C85} | 
| None | None | None | None | None | {448aee3b-dc65-4af6-bf5f-dce86d62b6c7} | 
| DFSRHelper.HealthReport Class | DFSRHelper.HealthReport Class | None | DFSRHelper.HealthReport Class | None | {4579476D-036C-430C-801F-60CBC4A6C059} | 
| Microsoft WBEM Unsecured Apartment | Microsoft WBEM Unsecured Apartment | None | Microsoft WBEM Unsecured Apartment | None | {49BD2028-1523-11D1-AD79-00C04FD8FDFF} | 
| UIAutomationCrossBitnessHook64 Class | UIAutomationCrossBitnessHook64 Class | None | UIAutomationCrossBitnessHook64 Class | None | {49f171dd-b51a-40d3-9a6c-52d674cc729d} | 
| Shell Security Editor | Shell Security Editor | None | Shell Security Editor | None | {4D111E08-CBF7-4f12-A926-2C7920AF52FC} | 
| Microsoft Volume Shadow Copy Service software provider | Microsoft Volume Shadow Copy Service software provider | None | Microsoft Volume Shadow Copy Service software provider | None | {4db9c793-c48d-449c-9754-46027ee45c94} | 
| COM+ Event System | COM+ Event System | None | COM+ Event System | None | {4E14FBA2-2E22-11D1-9964-00C04FBBB345} | 
| Shell Computer Accounts | Shell Computer Accounts | None | Shell Computer Accounts | None | {4f6bcd94-c2a5-42ce-8dbc-31e794be4630} | 
| %systemroot%\system32\intl.cpl | %systemroot%\system32\intl.cpl | None | %systemroot%\system32\intl.cpl | None | {514B5E31-5596-422F-BE58-D804464683B5} | 
| None | None | None | None | None | {515980c3-57fe-4c1e-a561-730dd256ab98} | 
| None | None | None | None | None | {51a1467f-96a2-4b1c-9632-4b4d950fe216} | 
| RemoteProxyFactory32 Class | RemoteProxyFactory32 Class | None | RemoteProxyFactory32 Class | None | {53362C32-A296-4F2D-A2F8-FD984D08340B} | 
| RemoteProxyFactory32 Class | RemoteProxyFactory32 Class | None | RemoteProxyFactory32 Class | None | {53362C64-A296-4F2D-A2F8-FD984D08340B} | 
| Virtual Disk Service Loader | Virtual Disk Service Loader | None | Virtual Disk Service Loader | None | {5364ED0E-493F-4B16-9DBF-AE486CF22660} | 
| Volume Shadow Copy Service | Volume Shadow Copy Service | None | Volume Shadow Copy Service | None | {56BE716B-2F76-4dfa-8702-67AE10044F0B} | 
| propshts | propshts | None | propshts | None | {59B8AFA0-229E-46d9-B980-DDA2C817EC7E} | 
| Authentication UI Terminal Services Bump Dialog | Authentication UI Terminal Services Bump Dialog | None | Authentication UI Terminal Services Bump Dialog | None | {59c7f6ec-7d18-412f-a68e-877982768e61} | 
| DFSRHelper.PropagationReport Class | DFSRHelper.PropagationReport Class | None | DFSRHelper.PropagationReport Class | None | {5DC19DE6-D228-4338-AAC4-2D1A1262CA7B} | 
| User OOBE Create User Object Server | User OOBE Create User Object Server | None | User OOBE Create User Object Server | None | {5f7f3f7b-1177-4d4b-b1db-bc6f671b8f25} | 
| None | None | None | None | None | {60173D16-A550-47f0-A14B-C6F9E4DA0831} | 
| UIAutomationCrossBitnessHook32 Class | UIAutomationCrossBitnessHook32 Class | None | UIAutomationCrossBitnessHook32 Class | None | {60a90a2f-858d-42af-8929-82be9d99e8a1} | 
| None | None | None | None | None | {63A53A38-004F-489B-BD61-96B5EEFADC04} | 
| Windows Update Agent | Windows Update Agent | None | Windows Update Agent | None | {653C5148-4DCE-4905-9CFD-1B23662D3D9E} | 
| None | None | None | None | None | {66eea0f5-001a-4073-a496-783f86fcf4c0} | 
| Background Intelligent Transfer Service | Background Intelligent Transfer Service | None | Background Intelligent Transfer Service | None | {69AD4AEE-51BE-439b-A92C-86AE490E8B30} | 
| SPPComApi | SPPComApi | None | SPPComApi | None | {6D9A7A40-DDCA-414E-B48E-DFB032C03C1B} | 
| TieringEngineService | TieringEngineService | None | TieringEngineService | None | {6DF5BCF4-22E9-446D-8763-A2C7677ECF7D} | 
| RSoPProv | RSoPProv | None | RSoPProv | None | {6EBBFC6C-B721-4D10-9371-5D8E8C76D315} | 
| EditionUpgradeHelper | EditionUpgradeHelper | None | EditionUpgradeHelper | None | {6F65B602-F798-4094-8A41-A2A61961E5E8} | 
| Windows Insider Service | Windows Insider Service | None | Windows Insider Service | None | {7006698d-2974-4091-a424-85dd0b909e23} | 
| None | None | None | None | None | {722b3793-5367-4446-b6bb-db89b05c1f24} | 
| Sharing Elevated Virtual Factory | Sharing Elevated Virtual Factory | None | Sharing Elevated Virtual Factory | None | {72A7994A-3092-4054-B6BE-08FF81AEEFFC} | 
| User Profile Service DCOM server | User Profile Service DCOM server | None | User Profile Service DCOM server | None | {72E3272B-4EEA-4104-B358-1A282E4FC1AD} | 
| Microsoft WMI Provider Subsystem Host | Microsoft WMI Provider Subsystem Host | None | Microsoft WMI Provider Subsystem Host | None | {73E709EA-5D93-4B2E-BBB0-99B7938DA9E4} | 
| Trusted Installer Service | Trusted Installer Service | None | Trusted Installer Service | None | {752073A2-23F2-4396-85F0-8FDB879ED0ED} | 
| PrintFilterPipelineSvc | PrintFilterPipelineSvc | None | PrintFilterPipelineSvc | None | {76db1bf3-e820-4765-a1b2-0b16a86b1950} | 
| Shell FMIFS Wrapper | Shell FMIFS Wrapper | None | Shell FMIFS Wrapper | None | {7aa7790d-75d7-484b-98a1-3913d022091d} | 
| EapThirdPartyDllHost | EapThirdPartyDllHost | None | EapThirdPartyDllHost | None | {7B130458-E09C-4823-A8AF-2583DCD9AEC7} | 
| Shell Create Object Local Server | Shell Create Object Local Server | None | Shell Create Object Local Server | None | {7B6EA1D5-03C2-4AE4-B21C-8D0515CC91B7} | 
| Microsoft Windows Remote Shell Host With User Settings | Microsoft Windows Remote Shell Host With User Settings | None | Microsoft Windows Remote Shell Host With User Settings | None | {7d378de6-ed8d-426d-91df-0273d07cd7f6} | 
| GPMC Reporting | GPMC Reporting | None | GPMC Reporting | None | {7f9bbc82-ba5f-4448-8622-ef76b8d007e6} | 
| Authentication UI CredUI Out of Proc Helper for AppContainer Clients | Authentication UI CredUI Out of Proc Helper for AppContainer Clients | None | Authentication UI CredUI Out of Proc Helper for AppContainer Clients | None | {7FC12E96-4CB7-4ABD-ADAA-EF7845B10629} | 
| CFmIfsEngine host | CFmIfsEngine host | None | CFmIfsEngine host | None | {82D94FB3-7FE6-4797-BB72-9A886C66073B} | 
| CustReg Class | CustReg Class | None | CustReg Class | None | {84D586C4-A423-11D2-B943-00C04F79D22F} | 
| ThirdPartyEapDispatcherPeerRuntime | ThirdPartyEapDispatcherPeerRuntime | None | ThirdPartyEapDispatcherPeerRuntime | None | {87BB326B-E4A0-4DE1-94F0-B9F41D0C6059} | 
| DFSRHelper.PropagationReport Class | DFSRHelper.PropagationReport Class | None | DFSRHelper.PropagationReport Class | None | {88B931BB-4810-457D-86B6-1F5911E9E084} | 
| Desktop Wallpaper Factory | Desktop Wallpaper Factory | None | Desktop Wallpaper Factory | None | {8B30085D-A3E3-44e3-AE7F-B03A1340EBED} | 
| None | None | None | None | None | {8B4B437E-4CAB-4e83-89F6-7F9F7DF414EA} | 
| Windows Management and Instrumentation | Windows Management and Instrumentation | None | Windows Management and Instrumentation | None | {8BC3F05E-D86B-11D0-A075-00C04FB68820} | 
| TSTheme | TSTheme | None | TSTheme | None | {8be0366c-8522-40be-8b08-cb26557f2854} | 
| None | None | None | None | None | {8C482DCE-2644-4419-AEFF-189219F916B9} | 
| TiWorker | TiWorker | None | TiWorker | None | {8D15A4F3-1BE5-4120-8A4D-2EF92A5DD58D} | 
| RdpSa | RdpSa | None | RdpSa | None | {8e7fae4d-cff0-41d3-a326-5a80470264bb} | 
| Shell Computer Groups | Shell Computer Groups | None | Shell Computer Groups | None | {8f3080a6-af99-4f2e-a806-f3d5702a0444} | 
| Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients | Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients | None | Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients | None | {924DC564-16A6-42EB-929A-9A61FA7DA06F} | 
| HtmlLocalFileResolver | HtmlLocalFileResolver | None | HtmlLocalFileResolver | None | {93AAD2A0-036A-4B11-A078-DA8776B38139} | 
| PenIMC4v2 | PenIMC4v2 | None | PenIMC4v2 | None | {953E4863-7AD1-4DAE-B2BD-108F1D57967B} | 
| DFSRHelper.HealthReport Class | DFSRHelper.HealthReport Class | None | DFSRHelper.HealthReport Class | None | {970B4475-63F0-4aa4-959C-AB8FFF3BD27C} | 
| PrintIsolationHost | PrintIsolationHost | None | PrintIsolationHost | None | {98a89e0c-1fde-4c2a-a373-b04831e6aa60} | 
| Shell Hardware Mixed Content Handler | Shell Hardware Mixed Content Handler | None | Shell Hardware Mixed Content Handler | None | {995C996E-D918-4a8c-A302-45719A6F4EA7} | 
| None | None | None | None | None | {9aa46009-3ce0-458a-a354-715610a075e6} | 
| timedate.cpl | timedate.cpl | None | timedate.cpl | None | {9df523b0-a6c0-4ea9-b5f1-f4565c3ac8b8} | 
| registryBrowser | registryBrowser | None | registryBrowser | None | {A3D9ED06-DDCB-4392-ADBF-205DB8B281C9} | 
| Shell ChkdskEx Dialog | Shell ChkdskEx Dialog | None | Shell ChkdskEx Dialog | None | {a4c31131-ff70-4984-afd6-0609ced53ad6} | 
| Virtual Factory for MaintenanceUI | Virtual Factory for MaintenanceUI | None | Virtual Factory for MaintenanceUI | None | {A6BFEA43-501F-456F-A845-983D3AD7B8F0} | 
| Microsoft Windows Defender | Microsoft Windows Defender | None | Microsoft Windows Defender | None | {A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F} | 
| None | None | None | None | None | {AA0B85DA-FDDF-4272-8D1D-FF9B966D75B0} | 
| DEFRAGSVC service | DEFRAGSVC service | None | DEFRAGSVC service | None | {ab7c873b-eb14-49a6-be60-a602f80e6d22} | 
| Out of proc server to enable Insider Hub scenarios to be reached from inside of its appcontainer | Out of proc server to enable Insider Hub scenarios to be reached from inside of its appcontainer | None | Out of proc server to enable Insider Hub scenarios to be reached from inside of its appcontainer | None | {ac0fd47a-37f4-4502-bfee-6b317e479d41} | 
| None | None | None | None | None | {b0316d0c-da2f-40e0-9f91-f600caf042dc} | 
| ThirdPartyEapDispatcherAuthenticatorRuntime | ThirdPartyEapDispatcherAuthenticatorRuntime | None | ThirdPartyEapDispatcherAuthenticatorRuntime | None | {B0E28D63-52F6-4E30-992B-78ECF97268E9} | 
| DFSRHelper.ADProxy Class | DFSRHelper.ADProxy Class | None | DFSRHelper.ADProxy Class | None | {B167BEB5-324D-4C2C-93D8-89F82AB8D75E} | 
| Windows Update Agent - Remote Access | Windows Update Agent - Remote Access | None | Windows Update Agent - Remote Access | None | {B366DEBE-645B-43A5-B865-DDD82C345492} | 
| Found New Hardware Wizard | Found New Hardware Wizard | None | Found New Hardware Wizard | None | {B6A32FE6-E29D-AEAE-A608-D273E40CA34C} | 
| Event Object Change 2 | Event Object Change 2 | None | Event Object Change 2 | None | {BB07BACD-CD56-4E63-A8FF-CBF0355FB9F4} | 
| EditionUpgradeManagerObj | EditionUpgradeManagerObj | None | EditionUpgradeManagerObj | None | {BD54C901-076B-434E-B6C7-17C531F4AB41} | 
| VM IC Heartbeat Service | VM IC Heartbeat Service | None | VM IC Heartbeat Service | None | {be0fc7f0-f248-4091-a123-34ca29a6901b} | 
| Shell AutoPlay Direct | Shell AutoPlay Direct | None | Shell AutoPlay Direct | None | {BF8841C9-378A-4CAD-B4FC-5091366CBC0D} | 
| None | None | None | None | None | {c8b67f54-d1cb-44bf-9103-a1ab9a9ed8ad} | 
| netprofm | netprofm | None | netprofm | None | {C96887DA-A652-4426-905E-4A37546F847C} | 
| editionupgradebroker | editionupgradebroker | None | editionupgradebroker | None | {C97E2AEF-AB0E-4FA6-BA29-1A1A7CCBA125} | 
| RCM | RCM | None | RCM | None | {C9F65BA8-1F8F-4382-AE27-C91FFB29275F} | 
| User OOBE Create Elevated Object Server | User OOBE Create Elevated Object Server | None | User OOBE Create Elevated Object Server | None | {ca8c87c1-929d-45ba-94db-ef8e6cb346ad} | 
| OpenSearch Description Create Search Connector Verb Handler | OpenSearch Description Create Search Connector Verb Handler | None | OpenSearch Description Create Search Connector Verb Handler | None | {CB1DFE3A-EDFF-4d1f-867D-8ADB02926F4B} | 
| PrintIsolationSessionHost | PrintIsolationSessionHost | None | PrintIsolationSessionHost | None | {CB363445-F453-4C1E-8EE4-BD123C5E394F} | 
| sppui | sppui | None | sppui | None | {CCFDD24D-CEAB-458B-A4F1-F884973395DF} | 
| PNPXAssoc.dll | PNPXAssoc.dll | None | PNPXAssoc.dll | None | {cee8ccc9-4f6b-4469-a235-5a22869eef03} | 
| Event Object Change | Event Object Change | None | Event Object Change | None | {D0565000-9DF4-11D1-A281-00C04FCA0AA7} | 
| Winmgmt MOF Compiler OOP | Winmgmt MOF Compiler OOP | None | Winmgmt MOF Compiler OOP | None | {D215781D-019E-4FA0-903D-0CDCDE13A4F5} | 
| None | None | None | None | None | {D3DCB472-7261-43ce-924B-0704BD730D5F} | 
| Microsoft Software Protection Platform Admin Object (outer) | Microsoft Software Protection Platform Admin Object (outer) | None | Microsoft Software Protection Platform Admin Object (outer) | None | {D8D4249F-A8FB-44A7-8AA0-564E8C385BD6} | 
| None | None | None | None | None | {DCED8DB0-11A5-4b16-AB9D-4E28CA38C99F} | 
| BrowserBrokerServer | BrowserBrokerServer | None | BrowserBrokerServer | None | {DD9C53BC-8441-4B94-BD0E-36E6E02A6D61} | 
| rundll32.exe | rundll32.exe | None | rundll32.exe | None | {de5d803e-5d2a-4b5f-9c63-af25a465cc44} | 
| LockScreen Call Broker | LockScreen Call Broker | None | LockScreen Call Broker | None | {DE7D3D65-5454-4EF5-9518-776739DAB39F} | 
| Profile Notification Host | Profile Notification Host | None | Profile Notification Host | None | {E10F6C3A-F1AE-4adc-AA9D-2FE65525666E} | 
| Immersive Print Dialog Surrogate | Immersive Print Dialog Surrogate | None | Immersive Print Dialog Surrogate | None | {E15FBAC2-C276-4523-92CA-561456EBCF3E} | 
| None | None | None | None | None | {E2B3C97F-6AE1-41AC-817A-F6F92166D7DD} | 
| Windows Update Agent User Interface for Published Applications | Windows Update Agent User Interface for Published Applications | None | Windows Update Agent User Interface for Published Applications | None | {e30984f1-b02b-4c27-a40f-23d11b8c1212} | 
| Execute Unknown | Execute Unknown | None | Execute Unknown | None | {e44e9428-bdbc-4987-a099-40dc8fd255e7} | 
| Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients (Failed Mouse In Pointer) | Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients (Failed Mouse In Pointer) | None | Authentication UI CredUI Out of Proc Helper for Non-AppContainer Clients (Failed Mouse In Pointer) | None | {E45A56CE-399C-45F0-9E6F-BFAACD3C711F} | 
| Orchestrator Service | Orchestrator Service | None | Orchestrator Service | None | {E7299E79-75E5-47BB-A03D-6D319FB7F886} | 
| File Prop Sheet Page Helper | File Prop Sheet Page Helper | None | File Prop Sheet Page Helper | None | {E96767E0-7EAA-45E1-8E7D-64414AFF281A} | 
| browser | browser | None | browser | None | {E9F570A3-EA8F-4CE9-9D59-C6AC35B9F403} | 
| Immersive Print Dialog Surrogate | Immersive Print Dialog Surrogate | None | Immersive Print Dialog Surrogate | None | {EB28E902-728E-42C4-97DC-DA89E144C744} | 
| None | None | None | None | None | {EC9846B3-2762-4A6B-A214-6ACB603462D2} | 
| ComEvents.ComServiceEvents | ComEvents.ComServiceEvents | None | ComEvents.ComServiceEvents | None | {ECABB0C3-7F19-11D2-978E-0000F8757E2A} | 
| ComEvents.ComSystemAppEventData | ComEvents.ComSystemAppEventData | None | ComEvents.ComSystemAppEventData | None | {ECABB0C6-7F19-11D2-978E-0000F8757E2A} | 
| Share Manager | Share Manager | None | Share Manager | None | {edb5f444-cb8d-445a-a523-ec5ab6ea33c7} | 
| polmkr | polmkr | None | polmkr | None | {EE81B265-32DD-41A0-878F-05B9A7C94D68} | 
| Virtual Disk Service | Virtual Disk Service | None | Virtual Disk Service | None | {F290BFB2-1864-45B1-8804-2654194A87E7} | 
| NDFAPI | NDFAPI | None | NDFAPI | None | {F3D3AA8D-EF96-4470-848E-BD70B803047A} | 
| None | None | None | None | None | {f735e733-d681-4aef-83c1-7ec82cac5ecc} | 
| WinInetBrokerServer | WinInetBrokerServer | None | WinInetBrokerServer | None | {F9717507-6651-4EDB-BFF7-AE615179BCCF} | 
| VssEvent | VssEvent | None | VssEvent | None | {FAF53CC4-BD73-4E36-83F1-2B23F46E513E} | 
| Shell Hardware Mixed Content Handler Cancelled | Shell Hardware Mixed Content Handler Cancelled | None | Shell Hardware Mixed Content Handler Cancelled | None | {fb479c02-9ec4-4fed-8599-debe037452cb} | 
| None | None | None | None | None | {ff9e6131-a8c1-4188-aa03-82e9f10a05a8} | 
| Shell Execute Hardware Event Handler | Shell Execute Hardware Event Handler | None | Shell Execute Hardware Event Handler | None | {FFB8655F-81B9-4fce-B89C-9A6BA76D13E7} |
```
#### Win32_COMApplicationClasses
```sh
WQL> SELECT * FROM Win32_COMApplicationClasses WHERE GroupComponent = "Win32_DCOMApplication.AppID=\"{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_ClassicComClass.ComponentId="{A2D75874-6750-4931-94C1-C99D3BC9D0C7}" | 
```
#### Win32_COMApplicationSettings
```sh
WQL> SELECT * FROM Win32_COMApplicationSettings WHERE Element = "Win32_DCOMApplication.AppID=\"{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}\""
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_DCOMApplicationSetting.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" |
```
#### Win32_COMClass
```sh
WQL> SELECT * FROM Win32_COMClass WHERE Caption = "Microsoft Windows Defender"
| Caption | Description | InstallDate | Name | Status | ComponentId | 
| Microsoft Windows Defender | Microsoft Windows Defender | None | Microsoft Windows Defender | None | {A2D75874-6750-4931-94C1-C99D3BC9D0C7} | 
```
#### Win32_ComClassAutoEmulator
#### Win32_ComClassEmulator
#### Win32_COMSetting
```sh
WQL> SELECT * FROM Win32_COMSetting WHERE Caption = "Microsoft Windows Defender"
| SettingID | Caption | Description | AppID | AuthenticationLevel | RemoteServerName | RunAsUser | EnableAtStorageActivation | UseSurrogate | CustomSurrogate | LocalService | ServiceParameters | 
| None | Microsoft Windows Defender | Microsoft Windows Defender | {A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F} | None | None | None | False | True | None | None | None | 
| None | Microsoft Windows Defender | Microsoft Windows Defender | {A2D75874-6750-4931-94C1-C99D3BC9D0C7} | None | {A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F} | Both | None | False | False | None | False | None | None | C:\Program Files\Windows Defender\MsMpCom.dll | None | None | None | None | None | None | None | None | None | None | None | 
```
#### Win32_DCOMApplication
```sh
WQL> SELECT * FROM Win32_DCOMApplication WHERE Caption = "Microsoft Windows Defender"
| Caption | Description | InstallDate | Name | Status | AppID | 
| Microsoft Windows Defender | Microsoft Windows Defender | None | Microsoft Windows Defender | None | {A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F} |
```
#### Win32_DCOMApplicationSetting
```sh
WQL> SELECT * FROM Win32_DCOMApplicationSetting WHERE Caption = "Microsoft Windows Defender"
| SettingID | Caption | Description | AppID | AuthenticationLevel | RemoteServerName | RunAsUser | EnableAtStorageActivation | UseSurrogate | CustomSurrogate | LocalService | ServiceParameters | 
| None | Microsoft Windows Defender | Microsoft Windows Defender | {A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F} | None | None | None | False | True | None | None | None |
```
#### Win32_DCOMApplicationAccessAllowedSetting
```sh
WQL> SELECT * FROM Win32_DCOMApplicationAccessAllowedSetting WHERE Element = "Win32_DCOMApplication.AppID=\"{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}\""
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-18" | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-10" | 
| \\FOREST\root\cimv2:Win32_DCOMApplication.AppID="{A79DB36D-6218-48e6-9EC9-DCBA9A39BF0F}" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-4" |
```
#### Win32_DCOMApplicationLaunchAllowedSetting	
```sh
WQL> SELECT * FROM Win32_DCOMApplicationLaunchAllowedSetting WHERE Element = "Win32_DCOMApplication.AppID=\"{A79DB36D-6218-weffw48e6-9EC9-DCBA9A39BF0F}\""
WQL> 
```
#### Win32_ComponentCategory
```sh
WQL> SELECT * FROM Win32_ComponentCategory WHERE Caption = "Active Scripting Engine with Authoring"
| Caption | Description | InstallDate | Name | Status | CategoryId | 
| Active Scripting Engine with Authoring | Active Scripting Engine with Authoring | None | Active Scripting Engine with Authoring | None | {0AEE2A92-BCBB-11D0-8C72-00C04FC2B085} | 
```
#### Win32_ImplementedCategory
```sh
WQL> SELECT * FROM Win32_ImplementedCategory WHERE Category = "Win32_ComponentCategory.CategoryId=\"{0AEE2A92-BCBB-11D0-8C72-00C04FC2B085}\""
| Category | Component | 
| \\FOREST\root\cimv2:Win32_ComponentCategory.CategoryId="{0AEE2A92-BCBB-11D0-8C72-00C04FC2B085}" | \\FOREST\root\cimv2:Win32_ClassicCOMClass.ComponentId="{B54F3742-5B07-11CF-A4B0-00AA004A55E8}" | 
| \\FOREST\root\cimv2:Win32_ComponentCategory.CategoryId="{0AEE2A92-BCBB-11D0-8C72-00C04FC2B085}" | \\FOREST\root\cimv2:Win32_ClassicCOMClass.ComponentId="{F414C261-6AC0-11CF-B6D1-00AA00BBBB58}" | 
```


### Desktop
#### Win32_Desktop
```sh
WQL> SELECT * FROM Win32_Desktop WHERE Name LIKE "%administrator%"
| SettingID | Caption | Description | BorderWidth | CoolSwitch | CursorBlinkRate | DragFullWindows | GridGranularity | IconSpacing | IconTitleFaceName | IconTitleSize | IconTitleWrap | Name | Pattern | ScreenSaverActive | ScreenSaverExecutable | ScreenSaverSecure | ScreenSaverTimeout | Wallpaper | WallpaperTiled | WallpaperStretched | 
| None | None | None | 1 | None | 530 | False | None | None | Segoe UI | 9 | True | HTB\Administrator | 0 | False | None | None | None | None | False | True |
```
#### Win32_Environment
```sh
WQL> SELECT * FROM Win32_Environment WHERE Caption = "<SYSTEM>\\Path"
| Caption | Description | InstallDate | Name | Status | SystemVariable | UserName | VariableValue | 
| <SYSTEM>\Path | <SYSTEM>\Path | None | Path | OK | True | <SYSTEM> | %SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\ |
```
#### Win32_TimeZone
```sh
WQL> SELECT * FROM Win32_TimeZone
| SettingID | Caption | Description | Bias | DaylightBias | DaylightDay | DaylightDayOfWeek | DaylightHour | DaylightMillisecond | DaylightMinute | DaylightMonth | DaylightName | DaylightSecond | DaylightYear | StandardBias | StandardDay | StandardDayOfWeek | StandardHour | StandardMillisecond | StandardMinute | StandardMonth | StandardName | StandardSecond | StandardYear | 
| None | (UTC-08:00) Pacific Time (US & Canada) | (UTC-08:00) Pacific Time (US & Canada) | -480 | -60 | 2 | 0 | 2 | 0 | 0 | 3 | Pacific Daylight Time | 0 | 0 | 0 | 1 | 0 | 2 | 0 | 0 | 11 | Pacific Standard Time | 0 | 0 |
```
#### Win32_UserDesktop
```sh
WQL> SELECT * FROM Win32_UserDesktop WHERE Element = "Win32_UserAccount.Domain=\"htb\",Name=\"administrator\"" 
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_UserAccount.Domain="HTB",Name="Administrator" | \\FOREST\root\cimv2:Win32_Desktop.Name="HTB\\Administrator" | 
```


### Drivers
#### Win32_SystemDriver
```sh
WQL> SELECT * FROM Win32_SystemDriver WHERE Caption = "TPM"
| Caption | Description | InstallDate | Name | Status | CreationClassName | StartMode | Started | SystemCreationClassName | SystemName | AcceptPause | AcceptStop | DesktopInteract | DisplayName | ErrorControl | PathName | ServiceType | StartName | State | TagId | ExitCode | ServiceSpecificExitCode | 
| TPM | TPM | None | TPM | OK | Win32_SystemDriver | Manual | False | Win32_ComputerSystem | FOREST | False | False | False | TPM | Normal | C:\Windows\system32\drivers\tpm.sys | Kernel Driver |  | Stopped | 5 | 1077 | 0 |
```


### File System
#### Win32_CIMLogicalDeviceCIMDataFile
```sh
WQL> SELECT * FROM Win32_CIMLogicalDeviceCIMDataFile WHERE PurposeDescription = "System Management BIOS Driver"
| Antecedent | Dependent | Purpose | PurposeDescription | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\MSSMBIOS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MSSMBIOS.SYS" | 2 | System Management BIOS Driver |
```
#### Win32_Directory
```sh
WQL> SELECT * FROM Win32_Directory WHERE caption = "C:\\"
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | 
| C:\ | C:\ | None | c:\ | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | True | CIM_LogicalFile | None | True | Win32_FileSystem | NTFS | None | None | True | 18446744073709551615 | True | True | True | Local Disk |  | None | None | c: |  |  |  | 18809343 |
```
#### Win32_DirectorySpecification
省略
```sh
WQL> SELECT * FROM Win32_DirectorySpecification
| Name | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | CheckID | Description | Caption | CheckMode | DirectoryType | DirectoryPath | DefaultDir | Directory | 
| C_x86_Runtime_Detection | 14.12.25810 | 2 | {E3819B64-3C56-3DD7-921D-00B011AD31DE} | 19 | TARGETDIR{E3819B64-3C56-3DD7-921D-00B011AD31DE}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR | 
| Servicing_Key_ProductFamily_x86 | 14.12.25810 | 2 | {C96DC6F1-894A-33E0-A8C1-3E9E7394FA28} | 19 | TARGETDIR{C96DC6F1-894A-33E0-A8C1-3E9E7394FA28}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR | 
| Servicing_Key_ProductEdition_x86 | 14.12.25810 | 2 | {1EA220DF-5B36-3289-B979-D06841E41888} | 19 | TARGETDIR{1EA220DF-5B36-3289-B979-D06841E41888}{7FED75A1-600C-394B-8376-712E2A8861F2} | SourceDir | SourceDir | True | 65535 | None | SourceDir | TARGETDIR |

~~~
```
#### Win32_DiskDriveToDiskPartition
```sh
WQL> SELECT * FROM Win32_DiskDriveToDiskPartition
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #0" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #1" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" |
```
#### Win32_DiskPartition
```sh
WQL> SELECT * FROM Win32_DiskPartition
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | Bootable | PrimaryPartition | BootPartition | DiskIndex | HiddenSectors | Index | RewritePartition | Size | StartingOffset | Type | 
| Disk #0, Partition #0 | GPT: Unknown | None | Disk #0, Partition #0 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 921600 | None | False | False | False | 0 | None | 0 | None | 471859200 | 135266304 | GPT: Unknown | 
| Disk #0, Partition #1 | GPT: System | None | Disk #0, Partition #1 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 202752 | None | True | True | True | 0 | None | 1 | None | 103809024 | 607125504 | GPT: System | 
| Disk #0, Partition #2 | GPT: Basic Data | None | Disk #0, Partition #2 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #2 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 40552448 | None | False | True | False | 0 | None | 2 | None | 20762853376 | 710934528 | GPT: Basic Data |
```
#### Win32_DiskQuota
```sh
WQL> SELECT * FROM Win32_DiskQuota
| QuotaVolume | User | Status | Limit | WarningLimit | DiskSpaceUsed | 
| Win32_LogicalDisk.DeviceID="C:" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 0 | 0 | 0 | 
| Win32_LogicalDisk.DeviceID="C:" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 0 | 0 | 0 |
```
#### Win32_LogicalDisk
```sh
WQL> SELECT * FROM Win32_LogicalDisk
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | FreeSpace | Size | Compressed | DriveType | FileSystem | MaximumComponentLength | ProviderName | SupportsFileBasedCompression | VolumeName | VolumeSerialNumber | MediaType | SupportsDiskQuotas | QuotasDisabled | QuotasIncomplete | QuotasRebuilding | VolumeDirty | 
| C: | Local Fixed Disk | None | C: | None | 65535 | Win32_LogicalDisk | None | True | C: | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 18446744073709551615 | None | 18446744073709551615 | None | 10267963392 | 20762849280 | False | 3 | NTFS | 255 | None | True |  | 61F2A88F | 12 | True | True | False | False | False |
```
#### Win32_LogicalDiskRootDirectory
```sh
WQL> SELECT * FROM Win32_LogicalDiskRootDirectory
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" |
```
#### Win32_LogicalDiskToPartition
```sh
WQL> SELECT * FROM Win32_LogicalDiskToPartition
| Antecedent | Dependent | StartingAddress | EndingAddress | 
| \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" | \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | 710934528 | 21473787903 |
```
#### Win32_MappedLogicalDisk
#### Win32_OperatingSystemAutochkSetting
```sh
WQL> SELECT * FROM Win32_OperatingSystemAutochkSetting
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_OperatingSystem=@ | \\FOREST\root\cimv2:Win32_AutochkSetting.SettingID="Microsoft Windows Server 2016 Standard|C:\\Windows|\\Device\\Harddisk0\\Partition4" |
```
#### Win32_QuotaSetting
```sh
WQL> SELECT * FROM Win32_QuotaSetting
| SettingID | Caption | Description | VolumePath | State | DefaultLimit | DefaultWarningLimit | ExceededNotification | WarningExceededNotification | 
| None | C: | C: | C:\ | 0 | -1 | -1 | False | False |
```
#### Win32_ShortcutFile
```sh
WQL> SELECT * FROM Win32_ShortcutFile WHERE target LIKE "%perfmon.msc%"
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | Version | Manufacturer | Target | 
| c:\programdata\microsoft\windows\start menu\programs\vmware\vmware tools\start vm statistics logging.lnk | c:\programdata\microsoft\windows\start menu\programs\vmware\vmware tools\start vm statistics logging.lnk | 20190922165619.352516-420 | c:\programdata\microsoft\windows\start menu\programs\vmware\vmware tools\start vm statistics logging.lnk | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | CIM_LogicalFile | 20190922165619.352516-420 | False | Win32_FileSystem | NTFS | 20190922165619.352516-420 | 20190922165619.352516-420 | True | 690 | True | False | False | Shortcut | c:\programdata\microsoft\windows\start menu\programs\vmware\vmware tools\startv~1.lnk | None | None | c: | \programdata\microsoft\windows\start menu\programs\vmware\vmware tools\ | start VM Statistics Logging | lnk | 18809343 | None | None | C:\Windows\system32\perfmon.msc |
```
#### Win32_SubDirectory
```sh
WQL> SELECT * FROM Win32_SubDirectory WHERE GroupComponent = "Win32_Directory.Name='C:\\'"
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\$RECYCLE.BIN" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Documents and Settings" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\PerfLogs" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Program Files" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Program Files (x86)" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Recovery" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\System Volume Information" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users" | 
| \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Windows" |
```
#### Win32_SystemPartitions
```sh
WQL> SELECT * FROM Win32_SystemPartitions
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #0" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #1" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" |
```
#### Win32_Volume
```sh
WQL> SELECT * FROM Win32_Volume
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | Capacity | Compressed | DriveLetter | DriveType | FileSystem | FreeSpace | IndexingEnabled | DirtyBitSet | Label | MaximumFileNameLength | Automount | QuotasEnabled | QuotasIncomplete | QuotasRebuilding | SerialNumber | SupportsDiskQuotas | SupportsFileBasedCompression | PageFilePresent | SystemVolume | BootVolume | 
| C:\ | None | None | C:\ | None | 65535 | None | None | True | \\?\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\ | None | None | True | 65535 | None | FOREST | None | None | True | 65535 | 4096 | None | 18446744073709551615 | None | 20762849280 | False | C: | 3 | NTFS | 10419834880 | True | False | None | 255 | True | False | False | False | 1643292815 | True | True | True | False | True | 
| \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | None | \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | 65535 | None | None | True | \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | None | True | 65535 | None | FOREST | None | None | True | 65535 | 4096 | None | 18446744073709551615 | None | 471855104 | False | None | 3 | NTFS | 130310144 | True | False | Recovery | 255 | True | False | False | False | 3077485790 | True | True | False | False | False |
```
#### Win32_VolumeQuota
```sh
WQL> SELECT * FROM Win32_VolumeQuota
| Element | Setting | 
| Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | Win32_QuotaSetting.VolumePath="C:\\" | 
| Win32_Volume.DeviceID="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" | Win32_QuotaSetting.VolumePath="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" |
```
#### Win32_VolumeQuotaSetting
```sh
WQL> SELECT * FROM Win32_VolumeQuotaSetting
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | \\FOREST\root\cimv2:Win32_QuotaSetting.VolumePath="C:\\" |
```
#### Win32_VolumeUserQuota
```sh
WQL> SELECT * FROM Win32_VolumeUserQuota
| Volume | Account | Status | Limit | WarningLimit | DiskSpaceUsed | 
| Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 18446744073709551615 | 18446744073709551615 | 0 | 
| Win32_Volume.DeviceID="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 18446744073709551615 | 18446744073709551615 | 0 |
```


### Job Objects
#### Win32_CollectionStatistics
```sh
WQL> SELECT * FROM Win32_CollectionStatistics
| Stats | Collection | 
| \\FOREST\root\cimv2:Win32_NamedJobObjectActgInfo.Name="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObjectActgInfo.Name="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" |
```
#### Win32_LUID
#### Win32_LUIDandAttributes
#### Win32_NamedJobObject
```sh
WQL> SELECT * FROM Win32_NamedJobObject
| CollectionID | Caption | Description | BasicUIRestrictions | 
| \wmi\provider\sub\system\host\job | None | None | 0 | 
| \wmi\provider\sub\system\special\host\job | None | None | 0 |
```
#### Win32_NamedJobObjectActgInfo
```sh
WQL> SELECT * FROM Win32_NamedJobObjectActgInfo
| Name | Description | Caption | TotalUserTime | TotalKernelTime | ThisPeriodTotalUserTime | ThisPeriodTotalKernelTime | TotalPageFaultCount | TotalProcesses | ActiveProcesses | TotalTerminatedProcesses | ReadOperationCount | WriteOperationCount | OtherOperationCount | ReadTransferCount | WriteTransferCount | OtherTransferCount | PeakProcessMemoryUsed | PeakJobMemoryUsed | 
| \wmi\provider\sub\system\host\job | None | None | 172031250 | 467343750 | 172031250 | 467343750 | 3167363 | 7 | 2 | 0 | 10001 | 9120 | 2223009 | 8742902 | 991528 | 119208014 | 24891392 | 32108544 | 
| \wmi\provider\sub\system\special\host\job | None | None | 2656250 | 468750 | 2656250 | 468750 | 7025 | 2 | 0 | 0 | 0 | 74 | 330 | 0 | 10515 | 2056 | 5730304 | 5730304 |
```
#### Win32_NamedJobObjectLimit
```sh
WQL> SELECT * FROM Win32_NamedJobObjectLimit
| Collection | Setting | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\special\\host\\job" |
```
#### Win32_NamedJobObjectLimitSetting
```sh
WQL> SELECT * FROM Win32_NamedJobObjectLimitSetting
| SettingID | Caption | Description | ProcessMemoryLimit | JobMemoryLimit | PerProcessUserTimeLimit | PerJobUserTimeLimit | LimitFlags | MinimumWorkingSetSize | MaximumWorkingSetSize | ActiveProcessLimit | Affinity | PriorityClass | SchedulingClass | 
| \wmi\provider\sub\system\host\job | None | None | 568868864 | 1073741824 | 0 | 0 | 11016 | 0 | 0 | 32 | 0 | 32 | 5 | 
| \wmi\provider\sub\system\special\host\job | None | None | 0 | 0 | 0 | 0 | 11016 | 0 | 0 | 32 | 0 | 32 | 5 |
```
#### Win32_NamedJobObjectProcess
```sh
WQL> SELECT * FROM Win32_NamedJobObjectProcess
| Collection | Member | 
| \\.\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\.\root\cimv2:Win32_Process.Handle="2456" | 
| \\.\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\.\root\cimv2:Win32_Process.Handle="2836" |
```
#### Win32_NamedJobObjectSecLimit
```sh
WQL> SELECT * FROM Win32_NamedJobObjectSecLimit
| Collection | Setting | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectSecLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObjectSecLimitSetting.SettingID="\\wmi\\provider\\sub\\system\\special\\host\\job" |
```
#### Win32_NamedJobObjectSecLimitSetting
```sh
WQL> SELECT * FROM Win32_NamedJobObjectSecLimitSetting
| SettingID | Caption | Description | SecurityLimitFlags | SIDsToDisable | RestrictedSIDs | PrivilegesToDelete | 
| \wmi\provider\sub\system\host\job | None | None | 0 | None | None | None | 
| \wmi\provider\sub\system\special\host\job | None | None | 0 | None | None | None |
```
#### Win32_NamedJobObjectStatistics
```sh
WQL> SELECT * FROM Win32_NamedJobObjectStatistics
| Stats | Collection | 
| \\FOREST\root\cimv2:Win32_NamedJobObjectActgInfo.Name="\\wmi\\provider\\sub\\system\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\host\\job" | 
| \\FOREST\root\cimv2:Win32_NamedJobObjectActgInfo.Name="\\wmi\\provider\\sub\\system\\special\\host\\job" | \\FOREST\root\cimv2:Win32_NamedJobObject.CollectionID="\\wmi\\provider\\sub\\system\\special\\host\\job" |
```
#### Win32_SIDandAttributes
#### Win32_TokenGroups
#### Win32_TokenPrivileges


### Memory and Page Files
#### Win32_PageFile
#### Win32_PageFileElementSetting	
#### Win32_PageFileSetting
#### Win32_PageFileUsage
```sh
WQL> SELECT * FROM Win32_PageFileUsage
| Caption | Description | InstallDate | Name | Status | AllocatedBaseSize | CurrentUsage | PeakUsage | TempPageFile | 
| C:\pagefile.sys | C:\pagefile.sys | 20190918100723.678412-420 | C:\pagefile.sys | None | 448 | 106 | 401 | False |
```


### Multimedia Audio or Visual
#### Win32_CodecFile


### Networking
#### Win32_ActiveRoute
#### Win32_IP4PersistedRouteTable
#### Win32_IP4RouteTable
```sh
WQL> SELECT * FROM Win32_IP4RouteTable
| Caption | Description | InstallDate | Name | Status | Destination | Mask | InterfaceIndex | NextHop | Type | Protocol | Age | Metric1 | Metric2 | Metric3 | Metric4 | Metric5 | Information | 
| 0.0.0.0 | 0.0.0.0 - 0.0.0.0 - 10.129.0.1 | None | 0.0.0.0 | None | 0.0.0.0 | 0.0.0.0 | 5 | 10.129.0.1 | 4 | 3 | 31005 | 25 | -1 | -1 | -1 | -1 | 0.0 | 
| 10.129.0.0 | 10.129.0.0 - 255.255.0.0 - 0.0.0.0 | None | 10.129.0.0 | None | 10.129.0.0 | 255.255.0.0 | 5 | 0.0.0.0 | 3 | 2 | 31005 | 281 | -1 | -1 | -1 | -1 | 0.0 | 
| 10.129.95.210 | 10.129.95.210 - 255.255.255.255 - 0.0.0.0 | None | 10.129.95.210 | None | 10.129.95.210 | 255.255.255.255 | 5 | 0.0.0.0 | 3 | 2 | 31005 | 281 | -1 | -1 | -1 | -1 | 0.0 | 
| 10.129.255.255 | 10.129.255.255 - 255.255.255.255 - 0.0.0.0 | None | 10.129.255.255 | None | 10.129.255.255 | 255.255.255.255 | 5 | 0.0.0.0 | 3 | 2 | 31005 | 281 | -1 | -1 | -1 | -1 | 0.0 | 
| 127.0.0.0 | 127.0.0.0 - 255.0.0.0 - 0.0.0.0 | None | 127.0.0.0 | None | 127.0.0.0 | 255.0.0.0 | 1 | 0.0.0.0 | 3 | 2 | 31012 | 331 | -1 | -1 | -1 | -1 | 0.0 | 
| 127.0.0.1 | 127.0.0.1 - 255.255.255.255 - 0.0.0.0 | None | 127.0.0.1 | None | 127.0.0.1 | 255.255.255.255 | 1 | 0.0.0.0 | 3 | 2 | 31012 | 331 | -1 | -1 | -1 | -1 | 0.0 | 
| 127.255.255.255 | 127.255.255.255 - 255.255.255.255 - 0.0.0.0 | None | 127.255.255.255 | None | 127.255.255.255 | 255.255.255.255 | 1 | 0.0.0.0 | 3 | 2 | 31012 | 331 | -1 | -1 | -1 | -1 | 0.0 | 
| 224.0.0.0 | 224.0.0.0 - 240.0.0.0 - 0.0.0.0 | None | 224.0.0.0 | None | 224.0.0.0 | 240.0.0.0 | 1 | 0.0.0.0 | 3 | 2 | 31012 | 331 | -1 | -1 | -1 | -1 | 0.0 | 
| 224.0.0.0 | 224.0.0.0 - 240.0.0.0 - 0.0.0.0 | None | 224.0.0.0 | None | 224.0.0.0 | 240.0.0.0 | 5 | 0.0.0.0 | 3 | 2 | 31011 | 281 | -1 | -1 | -1 | -1 | 0.0 | 
| 255.255.255.255 | 255.255.255.255 - 255.255.255.255 - 0.0.0.0 | None | 255.255.255.255 | None | 255.255.255.255 | 255.255.255.255 | 1 | 0.0.0.0 | 3 | 2 | 31012 | 331 | -1 | -1 | -1 | -1 | 0.0 | 
| 255.255.255.255 | 255.255.255.255 - 255.255.255.255 - 0.0.0.0 | None | 255.255.255.255 | None | 255.255.255.255 | 255.255.255.255 | 5 | 0.0.0.0 | 3 | 2 | 31011 | 281 | -1 | -1 | -1 | -1 | 0.0 | 
```
#### Win32_IP4RouteTableEvent
#### Win32_NetworkClient
```sh
WQL> SELECT * FROM Win32_NetworkClient
| Caption | Description | InstallDate | Name | Status | Manufacturer | 
| Workstation | LanmanWorkstation | None | Microsoft Windows Network | OK | Microsoft Corporation |
```
#### Win32_NetworkConnection
#### Win32_NetworkProtocol
```sh
WQL> SELECT * FROM Win32_NetworkProtocol
| Caption | Description | InstallDate | Name | Status | ConnectionlessService | GuaranteesDelivery | GuaranteesSequencing | MaximumAddressSize | MaximumMessageSize | MessageOriented | MinimumAddressSize | PseudoStreamOriented | SupportsBroadcasting | SupportsConnectData | SupportsDisconnectData | SupportsEncryption | SupportsExpeditedData | SupportsFragmentation | SupportsGracefulClosing | SupportsGuaranteedBandwidth | SupportsMulticasting | SupportsQualityofService | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [TCP/IP] | OK | False | True | True | 16 | 0 | False | 16 | False | False | False | False | False | True | None | True | False | False | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [UDP/IP] | OK | True | False | False | 16 | 65527 | True | 16 | False | True | False | False | False | False | None | False | False | True | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [TCP/IPv6] | OK | False | True | True | 28 | 0 | False | 28 | False | False | False | False | False | True | None | True | False | False | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [UDP/IPv6] | OK | True | False | False | 28 | 65527 | True | 28 | False | True | False | False | False | False | None | False | False | True | False | 
| RSVP | RSVP TCPv6 Service Provider | None | RSVP TCPv6 Service Provider | None | False | True | True | 28 | 0 | False | 28 | False | False | False | False | True | True | None | True | False | False | True | 
| RSVP | RSVP TCP Service Provider | None | RSVP TCP Service Provider | None | False | True | True | 16 | 0 | False | 16 | False | False | False | False | True | True | None | True | False | False | True | 
| RSVP | RSVP UDPv6 Service Provider | None | RSVP UDPv6 Service Provider | None | True | False | False | 28 | 65527 | True | 28 | False | True | False | False | True | False | None | False | False | True | True | 
| RSVP | RSVP UDP Service Provider | None | RSVP UDP Service Provider | None | True | False | False | 16 | 65527 | True | 16 | False | True | False | False | True | False | None | False | False | True | True | 
| Hyper-V | Hyper-V RAW | None | Hyper-V RAW | None | False | True | True | 36 | 0 | False | 36 | False | False | False | False | False | False | None | True | False | False | False | 
| vSockets | vSockets DGRAM | None | vSockets DGRAM | None | True | False | False | 16 | 0 | True | 16 | False | False | False | False | False | False | None | False | False | False | False | 
| vSockets | vSockets STREAM | None | vSockets STREAM | None | False | True | True | 16 | 0 | False | 16 | False | False | False | False | False | False | None | True | False | False | False |
```
#### Win32_NTDomain
```sh
WQL> SELECT * FROM Win32_NTDomain
| Caption | Description | InstallDate | Name | Status | CreationClassName | NameFormat | PrimaryOwnerContact | PrimaryOwnerName | Roles | DomainControllerName | DomainControllerAddress | DomainControllerAddressType | DomainGuid | DomainName | DnsForestName | DSPrimaryDomainControllerFlag | DSWritableFlag | DSGlobalCatalogFlag | DSDirectoryServiceFlag | DSKerberosDistributionCenterFlag | DSTimeServiceFlag | DSDnsControllerFlag | DSDnsDomainFlag | DSDnsForestFlag | DcSiteName | ClientSiteName | 
| HTB | HTB | None | Domain: HTB | OK | Win32_NTDomain | None | None | None | None | \\FOREST | \\dead:beef::4039:28df:14a7:eb85 | 1 | {DFF0C71A-A949-4B26-8C7B-52E3E2CB6EAB} | HTB | htb.local | True | True | True | True | True | True | False | False | True | Default-First-Site-Name | Default-First-Site-Name |
```
#### Win32_PingStatus
#### Win32_ProtocolBinding
```sh
WQL> SELECT * FROM Win32_ProtocolBinding
| Antecedent | Device | Dependent | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [TCP/IP]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="kdnic" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [UDP/IP]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="kdnic" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [TCP/IPv6]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="kdnic" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [UDP/IPv6]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="kdnic" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [TCP/IP]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="e1iexpress" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [UDP/IP]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="e1iexpress" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [TCP/IPv6]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="e1iexpress" | 
| \\FOREST\root\cimv2:Win32_NetworkProtocol.Name="MSAFD Tcpip [UDP/IPv6]" | \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="e1iexpress" |
```


### Operating System Events
#### Win32_ComputerShutdownEvent
#### Win32_ComputerSystemEvent
#### Win32_DeviceChangeEvent
#### Win32_ModuleLoadTrace
#### Win32_ModuleTrace
#### Win32_ProcessStartTrace
#### Win32_ProcessStopTrace
#### Win32_ProcessTrace
#### Win32_SystemConfigurationChangeEvent
#### Win32_SystemTrace
#### Win32_ThreadStartTrace
#### Win32_ThreadStopTrace
#### Win32_ThreadTrace
#### Win32_VolumeChangeEvent


### Operating System Settings
#### Win32_BootConfiguration
```sh
WQL> SELECT * FROM Win32_BootConfiguration
| SettingID | Caption | Description | BootDirectory | ConfigurationPath | LastDrive | Name | ScratchDirectory | TempDirectory | 
| None | \Device\Harddisk0\Partition2 | \Device\Harddisk0\Partition2 | C:\Windows | C:\Windows | C: | BootConfiguration | C:\Windows\system32\config\systemprofile\AppData\Local\Temp | C:\Windows\system32\config\systemprofile\AppData\Local\Temp |
```
#### Win32_ComputerSystem
```sh
WQL> SELECT * FROM Win32_ComputerSystem
| Caption | Description | InstallDate | Name | Status | CreationClassName | NameFormat | PrimaryOwnerContact | PrimaryOwnerName | Roles | InitialLoadInfo | LastLoadInfo | PowerManagementSupported | PowerManagementCapabilities | PowerState | ResetCapability | AutomaticResetBootOption | AutomaticManagedPagefile | AutomaticResetCapability | BootROMSupported | BootupState | CurrentTimeZone | DNSHostName | Domain | InfraredSupported | Manufacturer | Model | NetworkServerModeEnabled | OEMLogoBitmap | SupportContactDescription | SystemStartupDelay | SystemStartupOptions | SystemStartupSetting | SystemType | UserName | DomainRole | WakeUpType | OEMStringArray | BootOptionOnLimit | BootOptionOnWatchDog | ResetCount | ResetLimit | PauseAfterReset | PowerOnPasswordStatus | KeyboardPasswordStatus | AdminPasswordStatus | FrontPanelResetStatus | ChassisBootupState | PowerSupplyState | ThermalState | DaylightInEffect | EnableDaylightSavingsTime | NumberOfProcessors | NumberOfLogicalProcessors | TotalPhysicalMemory | PartOfDomain | PCSystemType | PCSystemTypeEx | Workgroup | SystemSKUNumber | SystemFamily | ChassisSKUNumber | BootStatus | HypervisorPresent | 
| FOREST | AT/AT COMPATIBLE | None | FOREST | OK | Win32_ComputerSystem | None | None | Windows User | 323 339 350 377 389 393  | None | None | True | None | 0 | 1 | True | True | True | True | Normal boot | -420 | FOREST | htb.local | False | VMware, Inc. | VMware7,1 | True | None | None | None | None | None | x64-based PC | None | 5 | 6 | [MS_VM_CERT/SHA1/27d66596a61c48dd3dc7216fd715126e33f59ae7] Welcome to the Virtual Machine  | 3 | 3 | -1 | -1 | 3932100000 | 0 | 3 | 1 | 3 | 3 | 3 | 3 | True | True | 1 | 2 | 2146447360 | True | 1 | 1 | None | None | None | None | 0 0 0 33 31 162 0 3 2 2  | True |
```
#### Win32_ComputerSystemProcessor
```sh
WQL> SELECT * FROM Win32_ComputerSystemProcessor
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" |
```
#### Win32_ComputerSystemProduct
```sh
WQL> SELECT * FROM Win32_ComputerSystemProduct
| Caption | Description | IdentifyingNumber | Name | SKUNumber | Vendor | Version | UUID | 
| Computer System Product | Computer System Product | VMware-42 14 e6 d4 ac b6 44 b0-7a a2 11 4c d5 f0 d2 d7 | VMware7,1 | None | VMware, Inc. | None | D4E61442-B6AC-B044-7AA2-114CD5F0D2D7 |
```
#### Win32_DependentService
```sh
WQL> SELECT * FROM Win32_DependentService WHERE Antecedent = "Win32_Service.Name=\"RemoteRegistry\""
| Antecedent | Dependent | TypeOfDependency | 
| \\FOREST\root\cimv2:Win32_Service.Name="RemoteRegistry" | \\FOREST\root\cimv2:Win32_Service.Name="Dfs" | 65535 | 
```
#### Win32_LoadOrderGroup
```sh
WQL> SELECT * FROM Win32_LoadOrderGroup WHERE GroupOrder = 1 OR GroupOrder = 74
| Caption | Description | InstallDate | Name | Status | GroupOrder | DriverEnabled | 
| System Reserved | System Reserved | None | System Reserved | OK | 1 | True | 
| Early-Launch | Early-Launch | None | Early-Launch | OK | 74 | False |
```
#### Win32_LoadOrderGroupServiceDependencies
```sh
WQL> SELECT * FROM Win32_LoadOrderGroupServiceDependencies
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_LoadOrderGroup.Name="NetBIOSGroup" | \\FOREST\root\cimv2:Win32_Service.Name="RemoteAccess" | 
| \\FOREST\root\cimv2:Win32_LoadOrderGroup.Name="SCSI CDROM Class" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="cdfs" |
```
#### Win32_LoadOrderGroupServiceMembers
```sh
WQL> SELECT * FROM Win32_LoadOrderGroupServiceMembers WHERE GroupComponent = "Win32_LoadOrderGroup.Name=\"System Reserved\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_LoadOrderGroup.Name="System Reserved" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="pcw" | 
```
#### Win32_OperatingSystem
```sh
WQL> SELECT * FROM Win32_OperatingSystem
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | Distributed | FreePhysicalMemory | FreeVirtualMemory | MaxProcessMemorySize | OSType | OtherTypeDescription | Version | LocalDateTime | CurrentTimeZone | SizeStoredInPagingFiles | FreeSpaceInPagingFiles | LastBootUpTime | MaxNumberOfProcesses | NumberOfLicensedUsers | NumberOfProcesses | NumberOfUsers | TotalSwapSpaceSize | TotalVirtualMemorySize | TotalVisibleMemorySize | BootDevice | MUILanguages | BuildNumber | OSArchitecture | BuildType | CodeSet | CountryCode | CSDVersion | DataExecutionPrevention_Available | DataExecutionPrevention_32BitApplications | DataExecutionPrevention_Drivers | DataExecutionPrevention_SupportPolicy | Debug | ForegroundApplicationBoost | Locale | Manufacturer | Organization | OSLanguage | OSProductSuite | OperatingSystemSKU | PlusProductID | PlusVersionNumber | Primary | RegisteredUser | SerialNumber | ServicePackMajorVersion | ServicePackMinorVersion | SystemDevice | SystemDirectory | SystemDrive | WindowsDirectory | EncryptionLevel | LargeSystemCache | SuiteMask | ProductType | PAEEnabled | PortableOperatingSystem | 
| Microsoft Windows Server 2016 Standard |  | 20190918100759.000000-420 | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | OK | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | False | 540748 | 956616 | 137438953344 | 18 | None | 10.0.14393 | 20250904084031.571000-420 | -420 | 458592 | 346660 | 20250903233416.493515-420 | None | 0 | 36 | 2 | 18446744073709551615 | 2554732 | 2096140 | \Device\HarddiskVolume3 | en-US  | 14393 | 64-bit | Multiprocessor Free | 1252 | 1 | None | True | True | True | 3 | False | 2 | 0409 | Microsoft Corporation |  | 1033 | 272 | 7 | None | None | True | Windows User | 00376-30821-30176-AA930 | 0 | 0 | \Device\HarddiskVolume4 | C:\Windows\system32 | C: | C:\Windows | 256 | None | 272 | 2 | None | False | 
```
#### Win32_OperatingSystemQFE
```sh
WQL> SELECT * FROM Win32_OperatingSystemQFE
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_OperatingSystem=@ | \\FOREST\root\cimv2:Win32_QuickFixEngineering.HotFixID="KB3199986",ServicePackInEffect="" | 
| \\FOREST\root\cimv2:Win32_OperatingSystem=@ | \\FOREST\root\cimv2:Win32_QuickFixEngineering.HotFixID="KB4512574",ServicePackInEffect="" | 
| \\FOREST\root\cimv2:Win32_OperatingSystem=@ | \\FOREST\root\cimv2:Win32_QuickFixEngineering.HotFixID="KB4103720",ServicePackInEffect="" | 
```
#### Win32_OSRecoveryConfiguration
```sh
WQL> SELECT * FROM Win32_OSRecoveryConfiguration
| SettingID | Caption | Description | AutoReboot | DebugFilePath | ExpandedDebugFilePath | MiniDumpDirectory | ExpandedMiniDumpDirectory | Name | OverwriteExistingDebugFile | SendAdminAlert | WriteDebugInfo | DebugInfoType | WriteToSystemLog | KernelDumpOnly | 
| None | None | None | True | %SystemRoot%\MEMORY.DMP | C:\Windows\MEMORY.DMP | %SystemRoot%\Minidump | C:\Windows\Minidump | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | True | False | True | 7 | True | False |
```
#### Win32_QuickFixEngineering
```sh
WQL> SELECT * FROM Win32_QuickFixEngineering
| Caption | Description | InstallDate | Name | Status | HotFixID | ServicePackInEffect | CSName | FixComments | InstalledBy | InstalledOn | 
| http://support.microsoft.com/?kbid=3199986 | Update | None | None | None | KB3199986 |  | FOREST |  | NT AUTHORITY\SYSTEM | 11/21/2016 | 
| http://support.microsoft.com/?kbid=4512574 | Security Update | None | None | None | KB4512574 |  | FOREST |  | HTB\Administrator | 9/18/2019 | 
| http://support.microsoft.com/?kbid=4103720 | Update | None | None | None | KB4103720 |  | FOREST |  | NT AUTHORITY\SYSTEM | 9/20/2019 |
```
#### Win32_StartupCommand
```sh
WQL> SELECT * FROM Win32_StartupCommand
| SettingID | Caption | Description | User | UserSID | Name | Location | Command | 
| None | VMware User Process | VMware User Process | Public | None | VMware User Process | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run | "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr |
```
#### Win32_SystemBootConfiguration
```sh
WQL> SELECT * FROM Win32_SystemBootConfiguration
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_BootConfiguration.Name="BootConfiguration" |
```
#### Win32_SystemDesktop
```sh
WQL> SELECT * FROM Win32_SystemDesktop 
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="NT AUTHORITY\\SYSTEM" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="NT AUTHORITY\\LOCAL SERVICE" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="NT AUTHORITY\\NETWORK SERVICE" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="HTB\\sebastien" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="HTB\\svc-alfresco" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="HTB\\Administrator" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name=".DEFAULT" |
```
#### Win32_SystemDevices
#### Win32_SystemLoadOrderGroups
```sh
WQL> SELECT * FROM Win32_SystemLoadOrderGroups WHERE PartComponent = "Win32_LoadOrderGroup.Name=\"System Reserved\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_LoadOrderGroup.Name="System Reserved" |
```
#### Win32_SystemNetworkConnections
#### Win32_SystemOperatingSystem
```sh
WQL> SELECT * FROM Win32_SystemOperatingSystem
| GroupComponent | PartComponent | PrimaryOS | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_OperatingSystem=@ | True |
```
#### Win32_SystemProcesses
省略
```sh
WQL> SELECT * FROM Win32_SystemProcesses
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Process.Handle="0" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Process.Handle="4" | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Process.Handle="268" | 

~~~
```
#### Win32_SystemProgramGroups
```sh
WQL> SELECT * FROM Win32_SystemProgramGroups WHERE Setting = "Win32_LogicalProgramGroup.Name='Default:Start Menu\\Programs\\Windows PowerShell'"
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Windows PowerShell" | 
```
#### Win32_SystemResources
省略
```sh
WQL> SELECT * FROM Win32_SystemResources
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DMAChannel.DMAChannel=4 |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967293 | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3758096384" | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1024" | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Environment.Name="ComSpec",UserName="<SYSTEM>" | 
~~~
```
#### Win32_SystemServices
```sh
WQL> SELECT * FROM Win32_SystemServices WHERE PartComponent = "Win32_Service.Name=\"WinDefend\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Service.Name="WinDefend" | 
```
#### Win32_SystemSetting
省略
```sh
WQL> SELECT * FROM Win32_SystemSetting
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_BootConfiguration.Name="BootConfiguration" |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Desktop.Name="NT AUTHORITY\\SYSTEM" | 
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_TimeZone.StandardName="Pacific Standard Time" |
~~~
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu" | 
~~~
```
#### Win32_SystemSystemDriver
```sh
WQL> SELECT * FROM Win32_SystemSystemDriver WHERE PartComponent = "Win32_SystemDriver.Name=\"pcw\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_SystemDriver.Name="pcw" |
```
#### Win32_SystemTimeZone
```sh
WQL> SELECT * FROM Win32_SystemTimeZone
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_TimeZone.StandardName="Pacific Standard Time" |
```
#### Win32_SystemUsers
```sh
WQL> SELECT * FROM Win32_SystemUsers WHERE PartComponent = "Win32_UserAccount.Domain=\"htb\",Name=\"administrator\"" 
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_UserAccount.Name="Administrator",Domain="HTB" |
```


### Processes
#### Win32_Process
```sh
WQL> SELECT * FROM Win32_Process WHERE caption = "powershell.exe"
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | CreationDate | Handle | KernelModeTime | OSCreationClassName | OSName | Priority | ExecutionState | TerminationDate | UserModeTime | WorkingSetSize | ExecutablePath | MaximumWorkingSetSize | MinimumWorkingSetSize | PageFaults | PageFileUsage | PeakPageFileUsage | PeakWorkingSetSize | ProcessId | QuotaNonPagedPoolUsage | QuotaPagedPoolUsage | QuotaPeakNonPagedPoolUsage | QuotaPeakPagedPoolUsage | WindowsVersion | ThreadCount | HandleCount | ParentProcessId | SessionId | PrivatePageCount | PeakVirtualSize | VirtualSize | ReadOperationCount | WriteOperationCount | OtherOperationCount | ReadTransferCount | WriteTransferCount | OtherTransferCount | CommandLine | 
| powershell.exe | powershell.exe | None | powershell.exe | None | Win32_ComputerSystem | FOREST | Win32_Process | 20250903233527.352261-420 | 3036 | 7413437500 | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | 6 | 65535 | None | 46128750000 | 504143872 | C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe | 1380 | 200 | 31700113 | 543464 | 671480 | 627732 | 3036 | 44 | 522 | 139 | 530 | 10.0.14393 | 12 | 410 | 988 | 0 | 556507136 | 2200181616640 | 2200169426944 | 353 | 2 | 38498979 | 4783486 | 160 | 709873028 | powershell.exe -ep bypass C:\Users\Administrator\Documents\revert.ps1 | 
```
#### Win32_ProcessStartup
#### Win32_Thread
```sh
WQL> SELECT * FROM Win32_Thread WHERE processhandle = "3036"
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | OSCreationClassName | OSName | ProcessCreationClassName | ProcessHandle | CreationClassName | Handle | Priority | ExecutionState | UserModeTime | KernelModeTime | ElapsedTime | PriorityBase | StartAddress | ThreadState | ThreadWaitReason | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 2972 | 6 | 65535 | 15 | 62 | 36668000 | 6 | 0 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 1480 | 8 | 65535 | 0 | 0 | 36668000 | 6 | 1461809264 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 2648 | 11 | 65535 | 31218 | 10046 | 36668000 | 8 | 1461809264 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 2380 | 8 | 65535 | 0 | 0 | 36667000 | 6 | 0 | 5 | 15 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3096 | 8 | 65535 | 0 | 0 | 36666000 | 6 | 1461809264 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3100 | 10 | 65535 | 4578968 | 730859 | 36666000 | 6 | 0 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3108 | 8 | 65535 | 0 | 0 | 36665000 | 6 | 1461809264 | 5 | 4 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3316 | 11 | 65535 | 0 | 0 | 36601000 | 7 | 1461809264 | 5 | 15 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3836 | 9 | 65535 | 0 | 0 | 11284000 | 6 | 1461809264 | 5 | 6 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3940 | 8 | 65535 | 0 | 0 | 214000 | 6 | 1461809264 | 5 | 15 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3692 | 8 | 65535 | 0 | 0 | 150000 | 6 | 1461809264 | 5 | 15 | 
| None | None | None | None | None | Win32_ComputerSystem | FOREST | Win32_OperatingSystem | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | Win32_Process | 3036 | Win32_Thread | 3428 | 8 | 65535 | 0 | 0 | 34000 | 6 | 1461809264 | 5 | 15 |
```


### Registry
#### Win32_Registry
```sh
WQL> SELECT * FROM Win32_Registry
| Caption | Description | InstallDate | Name | Status | CurrentSize | ProposedSize | MaximumSize | 
| Registry | Registry | 20190918100759.000000-420 | Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | OK | 52 | 4095 | 4095 |
```


### Scheduler Jobs
#### Win32_CurrentTime
```sh
WQL> SELECT * FROM Win32_CurrentTime
| Year | Month | Day | DayOfWeek | WeekInMonth | Quarter | Hour | Minute | Second | Milliseconds | 
| 2025 | 9 | 4 | 4 | 1 | 3 | 9 | 50 | 19 | None | 
| 2025 | 9 | 4 | 4 | 1 | 3 | 16 | 50 | 19 | None |
```
#### Win32_ScheduledJob
#### Win32_LocalTime
```sh
WQL> SELECT * FROM Win32_LocalTime
| Year | Month | Day | DayOfWeek | WeekInMonth | Quarter | Hour | Minute | Second | Milliseconds | 
| 2025 | 9 | 4 | 4 | 1 | 3 | 9 | 51 | 22 | None |
```
#### Win32_UTCTime
```sh
WQL> SELECT * FROM Win32_UTCTime
| Year | Month | Day | DayOfWeek | WeekInMonth | Quarter | Hour | Minute | Second | Milliseconds | 
| 2025 | 9 | 4 | 4 | 1 | 3 | 16 | 51 | 52 | None |
```


### Security
#### Win32_AccountSID
省略
```sh
WQL> SELECT * FROM Win32_AccountSID
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_SystemAccount.Domain="FOREST",Name="Everyone" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-1-0" | 
~~~
| \\FOREST\root\cimv2:Win32_UserAccount.Domain="HTB",Name="Administrator" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-21-3072663084-364016917-1341370565-500" | 
~~~
| \\FOREST\root\cimv2:Win32_Group.Domain="FOREST",Name="Account Operators" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-32-548" | 
~~~
```
#### Win32_ACE
#### Win32_LogicalFileAccess
#### Win32_LogicalFileAuditing
#### Win32_LogicalFileGroup
#### Win32_LogicalFileOwner
#### Win32_LogicalFileSecuritySetting
#### Win32_LogicalShareAccess
```sh
WQL> SELECT * FROM Win32_LogicalShareAccess
| SecuritySetting | Trustee | Type | Inheritance | AccessMask | GuidObjectType | GuidInheritedObjectType | 
| \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="NETLOGON" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-1-0" | 0 | 0 | 1179817 | None | None | 
| \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="NETLOGON" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-32-544" | 0 | 0 | 2032127 | None | None | 
| \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="SYSVOL" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-1-0" | 0 | 0 | 1179817 | None | None | 
| \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="SYSVOL" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-32-544" | 0 | 0 | 2032127 | None | None | 
| \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="SYSVOL" | \\FOREST\root\cimv2:Win32_SID.SID="S-1-5-11" | 0 | 0 | 2032127 | None | None |
```
#### Win32_LogicalShareAuditing
#### Win32_LogicalShareSecuritySetting
```sh
WQL> SELECT * FROM Win32_LogicalShareSecuritySetting
| SettingID | Caption | Description | ControlFlags | Name | 
| None | Security settings of NETLOGON | Security settings of NETLOGON | 32772 | NETLOGON | 
| None | Security settings of SYSVOL | Security settings of SYSVOL | 32772 | SYSVOL |
```
#### Win32_PrivilegesStatus
#### Win32_SecurityDescriptor
#### Win32_SecuritySetting
#### Win32_SecuritySettingAccess
#### Win32_SecuritySettingAuditing
#### Win32_SecuritySettingGroup
#### Win32_SecuritySettingOfLogicalFile
#### Win32_SecuritySettingOfLogicalShare
```sh
WQL> SELECT * FROM Win32_SecuritySettingOfLogicalShare
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_Share.Name="NETLOGON" | \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="NETLOGON" | 
| \\FOREST\root\cimv2:Win32_Share.Name="SYSVOL" | \\FOREST\root\cimv2:Win32_LogicalShareSecuritySetting.Name="SYSVOL" |
```
#### Win32_SecuritySettingOfObject
#### Win32_SecuritySettingOwner
#### Win32_SID
#### Win32_Trustee


### Services
#### Win32_BaseService
```sh
WQL> SELECT * FROM Win32_BaseService WHERE Name = "WinDefend"
| Caption | Description | InstallDate | Name | Status | CreationClassName | StartMode | Started | SystemCreationClassName | SystemName | AcceptPause | AcceptStop | DesktopInteract | DisplayName | ErrorControl | PathName | ServiceType | StartName | State | TagId | ExitCode | ServiceSpecificExitCode | CheckPoint | WaitHint | ProcessId | DelayedAutoStart | 
| Windows Defender Service | Helps protect users from malware and other potentially unwanted software | None | WinDefend | OK | Win32_Service | Auto | True | Win32_ComputerSystem | FOREST | False | True | False | Windows Defender Service | Normal | "C:\Program Files\Windows Defender\MsMpEng.exe" | Own Process | LocalSystem | Running | 0 | 0 | 0 | 0 | 0 | 1512 | False | 
```
#### Win32_Service
```sh
WQL> SELECT * FROM Win32_Service WHERE Name = "WinDefend"
| Caption | Description | InstallDate | Name | Status | CreationClassName | StartMode | Started | SystemCreationClassName | SystemName | AcceptPause | AcceptStop | DesktopInteract | DisplayName | ErrorControl | PathName | ServiceType | StartName | State | TagId | ExitCode | ServiceSpecificExitCode | CheckPoint | WaitHint | ProcessId | DelayedAutoStart | 
| Windows Defender Service | Helps protect users from malware and other potentially unwanted software | None | WinDefend | OK | Win32_Service | Auto | True | Win32_ComputerSystem | FOREST | False | True | False | Windows Defender Service | Normal | "C:\Program Files\Windows Defender\MsMpEng.exe" | Own Process | LocalSystem | Running | 0 | 0 | 0 | 0 | 0 | 1512 | False |
```


### Shares
#### Win32_DFSNode
#### Win32_DFSNodeTarget
#### Win32_DFSTarget
#### Win32_ServerConnection
#### Win32_ServerSession
```sh
WQL> SELECT * FROM Win32_ServerSession
| Caption | Description | InstallDate | Name | Status | ComputerName | UserName | ActiveTime | IdleTime | ResourcesOpened | SessionType | ClientType | TransportName | 
| None | None | None | None | None | [fe80::d4b3:e70e:967c:bf96] | FOREST$ | 7 | 2 | 0 | 2 |  |  |
```
#### Win32_ConnectionShare	
#### Win32_PrinterShare
#### Win32_SessionConnection	
#### Win32_SessionProcess
省略
```sh
WQL> SELECT * FROM Win32_SessionProcess
| Antecedent | Dependent | 
| \\.\root\cimv2:Win32_LogonSession.LogonId="999" | \\.\root\cimv2:Win32_Process.Handle="500" | 
| \\.\root\cimv2:Win32_LogonSession.LogonId="999" | \\.\root\cimv2:Win32_Process.Handle="588" | 
| \\.\root\cimv2:Win32_LogonSession.LogonId="999" | \\.\root\cimv2:Win32_Process.Handle="752" | 

~~~
```
#### Win32_ShareToDirectory
```sh
WQL> SELECT * FROM Win32_ShareToDirectory
| Share | SharedElement | 
| \\FOREST\root\cimv2:Win32_Share.Name="ADMIN$" | \\FOREST\root\cimv2:Win32_Directory.Name="c:\\windows" | 
| \\FOREST\root\cimv2:Win32_Share.Name="C$" | \\FOREST\root\cimv2:Win32_Directory.Name="c:\\" | 
| \\FOREST\root\cimv2:Win32_Share.Name="NETLOGON" | \\FOREST\root\cimv2:Win32_Directory.Name="c:\\windows\\sysvol\\sysvol\\htb.local\\scripts" | 
| \\FOREST\root\cimv2:Win32_Share.Name="SYSVOL" | \\FOREST\root\cimv2:Win32_Directory.Name="c:\\windows\\sysvol\\sysvol" |
```
#### Win32_Share
```sh
WQL> SELECT * FROM Win32_Share
| Caption | Description | InstallDate | Name | Status | AllowMaximum | MaximumAllowed | Path | Type | AccessMask | 
| Remote Admin | Remote Admin | None | ADMIN$ | OK | True | None | C:\Windows | 2147483648 | None | 
| Default share | Default share | None | C$ | OK | True | None | C:\ | 2147483648 | None | 
| Remote IPC | Remote IPC | None | IPC$ | OK | True | None |  | 2147483651 | None | 
| Logon server share  | Logon server share  | None | NETLOGON | OK | True | None | C:\Windows\SYSVOL\sysvol\htb.local\SCRIPTS | 0 | None | 
| Logon server share  | Logon server share  | None | SYSVOL | OK | True | None | C:\Windows\SYSVOL\sysvol | 0 | None | 
```


### Start Menu
#### Win32_LogicalProgramGroup
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroup WHERE Caption = 'Logical program group "Default:Start Menu\\Programs\\Windows PowerShell"'
| Caption | Description | InstallDate | Name | Status | GroupName | UserName | 
| Logical program group "Default:Start Menu\Programs\Windows PowerShell" | Logical program group "Default:Start Menu\Programs\Windows PowerShell" | 20160716061803.459804-420 | Default:Start Menu\Programs\Windows PowerShell | None | Start Menu\Programs\Windows PowerShell | Default |
```
#### Win32_LogicalProgramGroupDirectory
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupDirectory WHERE Antecedent = "Win32_LogicalProgramGroup.Name='Default:Start Menu\\Programs\\Windows PowerShell'"
| Antecedent | Dependent | 
| Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Windows PowerShell" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell" | 
```
#### Win32_LogicalProgramGroupItem
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupItem WHERE Caption = "Logical program group item 'Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk'" 
| Caption | Description | InstallDate | Name | Status | 
| Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | 20160716061805.256664-420 | Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk | None |
```
#### Win32_LogicalProgramGroupItemDataFile
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupItemDataFile WHERE Antecedent = "Win32_LogicalProgramGroupItem.Name='Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk'"
| Antecedent | Dependent | 
| Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" |
```
#### Win32_ProgramGroupContents
```sh
WQL> SELECT * FROM Win32_ProgramGroupContents WHERE GroupComponent = "Win32_LogicalProgramGroup.Name='Default:Start Menu\\Programs\\Windows PowerShell'"
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Windows PowerShell" | \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell (x86).lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Windows PowerShell" | \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" | 
```
#### Win32_ProgramGroupOrItem
```sh
WQL> SELECT * FROM Win32_ProgramGroupOrItem WHERE Caption = 'Logical program group "Default:Start Menu\\Programs\\Windows PowerShell"'
| Caption | Description | InstallDate | Name | Status | GroupName | UserName | 
| Logical program group "Default:Start Menu\Programs\Windows PowerShell" | Logical program group "Default:Start Menu\Programs\Windows PowerShell" | 20160716061803.459804-420 | Default:Start Menu\Programs\Windows PowerShell | None | Start Menu\Programs\Windows PowerShell | Default |
```


### Storage
#### Win32_ShadowBy
#### Win32_ShadowContext
```sh
WQL> SELECT * FROM Win32_ShadowContext
| SettingID | Caption | Description | Name | Persistent | ClientAccessible | NoAutoRelease | NoWriters | Transportable | NotSurfaced | HardwareAssisted | Differential | Plex | Imported | ExposedRemotely | ExposedLocally | 
| None | None | The AppRollback Win32_ShadowContext specifies a persistent and non auto-release shadow copy with writer involvement. | AppRollback | True | False | True | False | False | False | False | False | False | False | False | False | 
| None | None | The Backup Win32_ShadowContext is the standard backup context. Specifies an auto-release, non-persistent shadow copy in which writers are involved in the creation. | Backup | False | False | False | False | False | False | False | False | False | False | False | False | 
| None | None | The FileShareBackup Win32_ShadowContext specifies a non-persistent and auto-release shadow copy created without writer involvement. | FileShareBackup | False | False | False | True | False | False | False | False | False | False | False | False | 
| None | None | The ClientAccessible Win32_ShadowContext specifies a read-only, client-accessible shadow copy supporting the Previous Versions Server feature. Only the system provider (the default provider available on the system) can create this type of shadow copy. | ClientAccessible | True | True | True | True | False | False | False | False | False | False | False | False | 
| None | None | The All Win32_ShadowContext specifies all types of shadow copies. This context is used for shadow queries | All | True | True | True | True | True | True | True | True | True | True | True | True | 
| None | None | The NASRollback Win32_ShadowContext specifies a persistent, and non auto-release shadow copy without writer involvement. | NASRollback | True | False | True | True | False | False | False | False | False | False | False | False |
```
#### Win32_ShadowCopy
#### Win32_ShadowDiffVolumeSupport	
```sh
WQL> SELECT * FROM Win32_ShadowDiffVolumeSupport
| Antecedent | Dependent | 
| Win32_ShadowProvider.ID="{B5946137-7B9F-4925-AF80-51ABD60B20D5}" | Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | 
| Win32_ShadowProvider.ID="{B5946137-7B9F-4925-AF80-51ABD60B20D5}" | Win32_Volume.DeviceID="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" |
```
#### Win32_ShadowFor
#### Win32_ShadowOn
#### Win32_ShadowProvider
```sh
WQL> SELECT * FROM Win32_ShadowProvider
| Caption | Description | InstallDate | Name | Status | ID | CLSID | Type | Version | VersionID | 
| None | None | None | Microsoft File Share Shadow Copy provider | None | {89300202-3CEC-4981-9171-19F59559E0F2} | {FCE59DA7-7BAC-40DA-8D21-3E7311BA51CD} | 4 | 1.0.0.1 | {00000001-0000-0000-0001-000000000001} | 
| None | None | None | Microsoft Software Shadow Copy provider 1.0 | None | {B5946137-7B9F-4925-AF80-51ABD60B20D5} | {65EE1DBA-8FF4-4A58-AC1C-3470EE2F376A} | 1 | 1.0.0.7 | {00000001-0000-0000-0007-000000000001} |
```
#### Win32_ShadowStorage
#### Win32_ShadowVolumeSupport
```sh
WQL> SELECT * FROM Win32_ShadowVolumeSupport
| Antecedent | Dependent | 
| Win32_ShadowProvider.ID="{B5946137-7B9F-4925-AF80-51ABD60B20D5}" | Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | 
| Win32_ShadowProvider.ID="{B5946137-7B9F-4925-AF80-51ABD60B20D5}" | Win32_Volume.DeviceID="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" |
```
#### Win32_Volume
```sh
WQL> SELECT * FROM Win32_Volume
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | Capacity | Compressed | DriveLetter | DriveType | FileSystem | FreeSpace | IndexingEnabled | DirtyBitSet | Label | MaximumFileNameLength | Automount | QuotasEnabled | QuotasIncomplete | QuotasRebuilding | SerialNumber | SupportsDiskQuotas | SupportsFileBasedCompression | PageFilePresent | SystemVolume | BootVolume | 
| C:\ | None | None | C:\ | None | 65535 | None | None | True | \\?\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\ | None | None | True | 65535 | None | FOREST | None | None | True | 65535 | 4096 | None | 18446744073709551615 | None | 20762849280 | False | C: | 3 | NTFS | 10262810624 | True | False | None | 255 | True | False | False | False | 1643292815 | True | True | True | False | True | 
| \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | None | \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | 65535 | None | None | True | \\?\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\ | None | None | True | 65535 | None | FOREST | None | None | True | 65535 | 4096 | None | 18446744073709551615 | None | 471855104 | False | None | 3 | NTFS | 130310144 | True | False | Recovery | 255 | True | False | False | False | 3077485790 | True | True | False | False | False | 
```
#### Win32_VolumeUserQuota
```sh
WQL> SELECT * FROM Win32_VolumeUserQuota
| Volume | Account | Status | Limit | WarningLimit | DiskSpaceUsed | 
| Win32_Volume.DeviceID="\\\\?\\Volume{322d5750-0b70-481a-9f25-de96bb3e8e16}\\" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 18446744073709551615 | 18446744073709551615 | 0 | 
| Win32_Volume.DeviceID="\\\\?\\Volume{d4ee34c8-9b77-4fe1-9439-107039a4e95f}\\" | Win32_Account.Domain="FOREST",Name="Administrators" | 0 | 18446744073709551615 | 18446744073709551615 | 0 |
```


### Users
#### Win32_Account
```sh
WQL> SELECT * FROM Win32_Account WHERE Name = "administrator"
| Caption | Description | InstallDate | Name | Status | Domain | SID | SIDType | LocalAccount | AccountType | Disabled | FullName | Lockout | PasswordChangeable | PasswordExpires | PasswordRequired | 
| HTB\administrator | Built-in account for administering the computer/domain | None | administrator | OK | HTB | S-1-5-21-3072663084-364016917-1341370565-500 | 1 | False | 512 | False | Administrator | False | True | True | True |
```
#### Win32_Group
```sh
WQL> SELECT * FROM Win32_Group WHERE Name = "administrators"
| Caption | Description | InstallDate | Name | Status | Domain | SID | SIDType | LocalAccount | 
| FOREST\Administrators | Administrators have complete and unrestricted access to the computer/domain | None | Administrators | OK | FOREST | S-1-5-32-544 | 4 | True |
```
#### Win32_GroupInDomain
```sh
WQL> SELECT * FROM Win32_GroupInDomain WHERE PartComponent = "Win32_Group.Domain=\"HTB\",Name=\"Domain Admins\""
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_NTDomain.Name="Domain: HTB" | \\FOREST\root\cimv2:Win32_Group.Domain="HTB",Name="Domain Admins" |
```
#### Win32_GroupUser
```sh
WQL> SELECT * FROM Win32_GroupUser WHERE GroupComponent = 'Win32_Group.Domain="forest",Name="administrators"'
| GroupComponent | PartComponent | 
| Win32_Group.Domain="forest",Name="administrators" | \\FOREST\root\cimv2:Win32_UserAccount.Domain="HTB",Name="Administrator" | 
| Win32_Group.Domain="forest",Name="administrators" | \\FOREST\root\cimv2:Win32_Group.Domain="HTB",Name="Enterprise Admins" | 
| Win32_Group.Domain="forest",Name="administrators" | \\FOREST\root\cimv2:Win32_Group.Domain="HTB",Name="Domain Admins" | 
```
#### Win32_LogonSession
省略
```sh
WQL> SELECT * FROM Win32_LogonSession
| Caption | Description | InstallDate | Name | Status | StartTime | LogonId | AuthenticationPackage | LogonType | 
| None | None | None | None | None | 20250905043531.797911-420 | 999 | Negotiate | 0 |
~~~
| None | None | None | None | None | 20250905043716.048128-420 | 246059 | Kerberos | 3 | 
~~~
| None | None | None | None | None | 20250905043708.641892-420 | 245677 | NTLM | 3 | 
~~~
```
#### Win32_LogonSessionMappedDisk
#### Win32_NetworkLoginProfile
```sh
WQL> SELECT * FROM Win32_NetworkLoginProfile
| SettingID | Caption | Description | AccountExpires | AuthorizationFlags | BadPasswordCount | CodePage | Comment | CountryCode | Flags | FullName | HomeDirectory | HomeDirectoryDrive | LastLogoff | LastLogon | LogonHours | LogonServer | MaximumStorage | Name | NumberOfLogons | Parameters | PasswordAge | PasswordExpires | PrimaryGroupId | Privileges | Profile | ScriptPath | UnitsPerWeek | UserComment | UserId | UserType | Workstations | 
| None | NT AUTHORITY\SYSTEM | Network login profile settings for SYSTEM on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\SYSTEM | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | NT AUTHORITY\LOCAL SERVICE | Network login profile settings for LOCAL SERVICE on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\LOCAL SERVICE | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | NT AUTHORITY\NETWORK SERVICE | Network login profile settings for NETWORK SERVICE on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\NETWORK SERVICE | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | sebastien | Network login profile settings for Sebastien Caron on HTB | None | 0 | 0 | 0 |  | 0 | 66113 | Sebastien Caron |  |  | **************.******+*** | 20190922152929.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\sebastien | 8 |  | 00002174153832.000000:000 | None | 513 | 1 |  |  | 168 |  | 1145 | Normal Account |  | 
| None | svc-alfresco | Network login profile settings for svc-alfresco on HTB | None | 0 | 0 | 0 |  | 0 | 4260353 | svc-alfresco |  |  | **************.******+*** | 20250902073300.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\svc-alfresco | 6 |  | 00000000000130.000000:000 | None | 513 | 1 |  |  | 168 |  | 1147 | Normal Account |  | 
| None | Administrator | Network login profile settings for Administrator on HTB | None | 0 | 0 | 0 | Built-in account for administering the computer/domain | 0 | 513 | Administrator |  |  | **************.******+*** | 20250901054943.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\Administrator | 143 |  | 00001463151633.000000:000 | None | 513 | 2 |  |  | 168 |  | 500 | Normal Account |  |
```
#### Win32_SystemAccount
```sh
WQL> SELECT * FROM Win32_SystemAccount WHERE Name = "system"
| Caption | Description | InstallDate | Name | Status | Domain | SID | SIDType | LocalAccount | 
| FOREST\SYSTEM | FOREST\SYSTEM | None | SYSTEM | OK | FOREST | S-1-5-18 | 5 | True |
```
#### Win32_UserAccount
```sh
WQL> SELECT * FROM Win32_UserAccount WHERE Name = "administrator"
| Caption | Description | InstallDate | Name | Status | Domain | SID | SIDType | LocalAccount | AccountType | Disabled | FullName | Lockout | PasswordChangeable | PasswordExpires | PasswordRequired | 
| HTB\administrator | Built-in account for administering the computer/domain | None | administrator | OK | HTB | S-1-5-21-3072663084-364016917-1341370565-500 | 1 | False | 512 | False | Administrator | False | True | True | True |
```
#### Win32_UserInDomain
```sh
WQL> SELECT * FROM Win32_UserInDomain WHERE PartComponent= 'Win32_UserAccount.Domain="HTB",Name="Administrator"'
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_NTDomain.Name="Domain: HTB" | \\FOREST\root\cimv2:Win32_UserAccount.Domain="HTB",Name="Administrator" | 
```


### Windows Event Log
#### Win32_NTEventlogFile
```sh
WQL> SELECT * FROM Win32_NTEventlogFile
| Caption | Description | InstallDate | Name | Status | InUseCount | Archive | CSCreationClassName | CSName | Compressed | CreationClassName | CreationDate | Encrypted | FSCreationClassName | FSName | LastAccessed | LastModified | Readable | FileSize | Writeable | Hidden | System | FileType | EightDotThreeFileName | CompressionMethod | EncryptionMethod | Drive | Path | FileName | Extension | AccessMask | Version | Manufacturer | LogfileName | MaxFileSize | NumberOfRecords | OverWritePolicy | OverwriteOutDated | Sources | 
| c:\windows\system32\winevt\logs\active directory web services.evtx | c:\windows\system32\winevt\logs\active directory web services.evtx | 20190918104258.718454-420 | C:\Windows\System32\Winevt\Logs\Active Directory Web Services.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918104258.718454-420 | False | Win32_FileSystem | NTFS | 20190918104258.718454-420 | 20250905043701.532600-420 | True | 69632 | True | False | False | evtx File | c:\windows\system32\winevt\logs\active~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Active Directory Web Services | evtx | None | None | None | Active Directory Web Services | 1052672 | 288 | WhenNeeded | 0 | Active Directory Web Services ADWS  | 
| c:\windows\system32\winevt\logs\application.evtx | c:\windows\system32\winevt\logs\application.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\Application.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20250905043618.641774-420 | True | 7409664 | True | False | False | evtx File | c:\windows\system32\winevt\logs\applic~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Application | evtx | None | None | None | Application | 20971520 | 2332 | WhenNeeded | 0 | Application .NET Runtime .NET Runtime Optimization Service Application Error Application Hang Application Management AutoEnrollment CardSpace 4.0.0.0 CertCa CertCli CertEnroll Chkdsk COM COM+ DiskQuota DSReplicationProvider Error Instrument ESENT EventSystem FssProv Group Policy Applications Group Policy Client Group Policy Data Sources Group Policy Device Settings Group Policy Drive Maps Group Policy Environment Group Policy Files Group Policy Folder Options Group Policy Folders Group Policy HTML View Extension Group Policy Ini Files Group Policy Internet Settings Group Policy Local Users and Groups Group Policy Mail Profiles Group Policy Management Group Policy Network Options Group Policy Network Shares Group Policy Power Options Group Policy Printers Group Policy Regional Options Group Policy Registry Group Policy Scheduled Tasks Group Policy Services Group Policy Shortcuts Group Policy Standard Edition Group Policy Start Menu Settings GroupPolicy ipmiprv LoadPerf Microsoft-Windows-ApplicationExperienceInfrastructure Microsoft-Windows-AppModel-Runtime Microsoft-Windows-AppModel-State Microsoft-Windows-ASN1 Microsoft-Windows-Audit-CVE Microsoft-Windows-Backup Microsoft-Windows-BestPractices Microsoft-Windows-CAPI2 Microsoft-Windows-CertificateServicesClient Microsoft-Windows-CertificateServicesClient-AutoEnrollment Microsoft-Windows-CertificateServicesClient-CertEnroll Microsoft-Windows-CertificateServicesClient-CredentialRoaming Microsoft-Windows-CertificationAuthorityClient-CertCli Microsoft-Windows-COMRuntime Microsoft-Windows-Crypto-BCrypt Microsoft-Windows-Crypto-DPAPI Microsoft-Windows-Crypto-DSSEnh Microsoft-Windows-Crypto-NCrypt Microsoft-Windows-Crypto-RSAEnh Microsoft-Windows-Defrag Microsoft-Windows-DeviceGuard Microsoft-Windows-DirectoryServices-Deployment Microsoft-Windows-EapHost Microsoft-Windows-EFS Microsoft-Windows-EventCollector Microsoft-Windows-FederationServices-Deployment Microsoft-Windows-FileServices-ServerManager-EventProvider Microsoft-Windows-GenericRoaming Microsoft-Windows-KdsSvc Microsoft-Windows-LoadPerf Microsoft-Windows-Management-UI Microsoft-Windows-PerfCtrs Microsoft-Windows-PerfNet Microsoft-Windows-PerfOS Microsoft-Windows-PerfProc Microsoft-Windows-propsys Microsoft-Windows-Rdms-UI Microsoft-Windows-RestartManager Microsoft-Windows-RPC-Events Microsoft-Windows-Security-Netlogon Microsoft-Windows-ServerManager-MultiMachine Microsoft-Windows-SmartCard-DeviceEnum Microsoft-Windows-SoftwareRestrictionPolicies Microsoft-Windows-User Profiles General Microsoft-Windows-User Profiles Service Microsoft-Windows-User-Loader Microsoft-Windows-Winsrv Microsoft-Windows-WMI Microsoft.Transactions.Bridge 4.0.0.0 MSDTC MSDTC 2 MSDTC Client MSDTC Client 2 MsiInstaller PDH PerfCtrs PerfDisk Perflib PerfNet PerfOs PerfProc Process Exit Monitor Profsvc SceCli SceSrv ServiceModel Audit 4.0.0.0 SideBySide Software Installation Software Protection Platform Service Standard TCP/IP Port System.IdentityModel 4.0.0.0 System.IO.Log 4.0.0.0 System.Runtime.Serialization 4.0.0.0 System.ServiceModel 4.0.0.0 TrustMonitor usbperf Userenv vmStatsProvider vmtools VMUpgradeHelper VMware Tools VSS WerSvc Windows Error Reporting Wininit Winlogon WinMgmt Wlclntfy WMI.NET Provider Extension Wow64 Emulation Layer  | 
| c:\windows\system32\winevt\logs\dfs replication.evtx | c:\windows\system32\winevt\logs\dfs replication.evtx | 20190918104258.780954-420 | C:\Windows\System32\Winevt\Logs\DFS Replication.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918104258.780954-420 | False | Win32_FileSystem | NTFS | 20190918104258.780954-420 | 20250905043659.313726-420 | True | 69632 | True | False | False | evtx File | c:\windows\system32\winevt\logs\dfsrep~1.evt | None | None | c: | \windows\system32\winevt\logs\ | DFS Replication | evtx | None | None | None | DFS Replication | 15532032 | 243 | WhenNeeded | 0 | DFS Replication DFSR  | 
| c:\windows\system32\winevt\logs\directory service.evtx | c:\windows\system32\winevt\logs\directory service.evtx | 20190918104258.796581-420 | C:\Windows\System32\Winevt\Logs\Directory Service.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918104258.796581-420 | False | Win32_FileSystem | NTFS | 20190918104258.796581-420 | 20250905043644.360993-420 | True | 1052672 | True | False | False | evtx File | c:\windows\system32\winevt\logs\direct~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Directory Service | evtx | None | None | None | Directory Service | 1052672 | 2763 | WhenNeeded | 0 | Directory Service NTDS API NTDS Backup NTDS Database NTDS General NTDS Inter-site Messaging NTDS ISAM NTDS KCC NTDS LDAP NTDS MAPI NTDS Replication NTDS SAM NTDS Scripting NTDS SDPROP NTDS Security NTDS Setup NTDS XDS  | 
| c:\windows\system32\winevt\logs\dns server.evtx | c:\windows\system32\winevt\logs\dns server.evtx | 20190918104540.171898-420 | C:\Windows\System32\Winevt\Logs\DNS Server.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918104540.171898-420 | False | Win32_FileSystem | NTFS | 20190918104540.171898-420 | 20250905043644.360993-420 | True | 1118208 | True | False | False | evtx File | c:\windows\system32\winevt\logs\dnsser~1.evt | None | None | c: | \windows\system32\winevt\logs\ | DNS Server | evtx | None | None | None | DNS Server | 104857600 | 273 | WhenNeeded | 0 | DNS Server DNS  | 
| c:\windows\system32\winevt\logs\hardwareevents.evtx | c:\windows\system32\winevt\logs\hardwareevents.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\HardwareEvents.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20190918100738.615947-420 | True | 69632 | True | False | False | evtx File | c:\windows\system32\winevt\logs\hardwa~1.evt | None | None | c: | \windows\system32\winevt\logs\ | HardwareEvents | evtx | None | None | None | HardwareEvents | 20971520 | 0 | WhenNeeded | 0 | HardwareEvents Microsoft-Windows-WSMAN-SEL_LogRecord  | 
| c:\windows\system32\winevt\logs\internet explorer.evtx | c:\windows\system32\winevt\logs\internet explorer.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\Internet Explorer.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20190918100738.615947-420 | True | 69632 | True | False | False | evtx File | c:\windows\system32\winevt\logs\intern~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Internet Explorer | evtx | None | None | None | Internet Explorer | 1052672 | 0 | WhenNeeded | 0 | Internet Explorer  | 
| c:\windows\system32\winevt\logs\key management service.evtx | c:\windows\system32\winevt\logs\key management service.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\Key Management Service.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20190918100738.615947-420 | True | 69632 | True | False | False | evtx File | c:\windows\system32\winevt\logs\keyman~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Key Management Service | evtx | None | None | None | Key Management Service | 20971520 | 0 | WhenNeeded | 0 | Key Management Service KmsRequests  | 
| c:\windows\system32\winevt\logs\security.evtx | c:\windows\system32\winevt\logs\security.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\Security.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20250905043647.798068-420 | True | 66129920 | True | False | False | evtx File | c:\windows\system32\winevt\logs\securi~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Security | evtx | None | None | None | Security | 134217728 | 100632 | WhenNeeded | 0 | Security DS LSA Microsoft-Windows-Eventlog Microsoft-Windows-Security-Auditing SC Manager Security Account Manager ServiceModel 4.0.0.0 Spooler TCP/IP VSSAudit  | 
| c:\windows\system32\winevt\logs\system.evtx | c:\windows\system32\winevt\logs\system.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\System.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20250905043544.563618-420 | True | 3215360 | True | False | False | evtx File | c:\windows\system32\winevt\logs\system~1.evt | None | None | c: | \windows\system32\winevt\logs\ | System | evtx | None | None | None | System | 20971520 | 5870 | WhenNeeded | 0 | System 3ware ACPI ADP80XX AFD AmdK8 AmdPPM amdsata amdsbs amdxata Application Management Group Policy Application Popup arcsas AsyncMac atapi b06bdrv BasicRender bfadfcoei bfadi Bowser Browser BugCheck bxfcoe bxois cdrom cht4iscsi cht4vbd DCOM DfsSvc Dhcp Dhcpv6 disk Display Dnsapi Dnscache e1iexpress ebdrv elxfcoe elxstor eventlog exFAT FltMgr HpSAMD Http i8042prt iaStorAV iaStorV ibbus intelppm IPMGM IPMIDRV IPNATHLP IPRouterManager isapnp iScsiPrt kbdclass kbdhid KDC kdnic Kerberos lltdio LmHosts LsaSrv LSI_SAS LSI_SAS2i LSI_SAS3i LSI_SSS LSM megasas megasr Microsoft-Pef-WFP-MessageProvider Microsoft-Windows-Audit-CVE Microsoft-Windows-Bits-Client Microsoft-Windows-CoreSystem-NetProvision-JoinProviderOnline Microsoft-Windows-DFSN-Server Microsoft-Windows-DFSN-ServerFilter Microsoft-Windows-DfsSvc Microsoft-Windows-Dhcp-Client Microsoft-Windows-DHCPv6-Client Microsoft-Windows-Diagnostics-Networking Microsoft-Windows-Directory-Services-SAM Microsoft-Windows-DistributedCOM Microsoft-Windows-DNS-Client Microsoft-Windows-DriverFrameworks-UserMode Microsoft-Windows-EventCollector Microsoft-Windows-Eventlog Microsoft-Windows-exFAT-SQM Microsoft-Windows-Fat-SQM Microsoft-Windows-FilterManager Microsoft-Windows-Firewall Microsoft-Windows-FMS Microsoft-Windows-FunctionDiscoveryHost Microsoft-Windows-GPIO-ClassExtension Microsoft-Windows-GroupPolicy Microsoft-Windows-HAL Microsoft-Windows-HttpEvent Microsoft-Windows-Iphlpsvc Microsoft-Windows-IsolatedUserMode Microsoft-Windows-Kernel-Boot Microsoft-Windows-Kernel-General Microsoft-Windows-Kernel-Interrupt-Steering Microsoft-Windows-Kernel-IO Microsoft-Windows-Kernel-PnP Microsoft-Windows-Kernel-Power Microsoft-Windows-Kernel-Processor-Power Microsoft-Windows-Kernel-WHEA Microsoft-Windows-Kernel-XDV Microsoft-Windows-LanguagePackSetup Microsoft-Windows-MountMgr Microsoft-Windows-MsLbfoSysEvtProvider Microsoft-Windows-NDIS Microsoft-Windows-NdisImPlatformSysEvtProvider Microsoft-Windows-Ntfs Microsoft-Windows-Ntfs-UBPM Microsoft-Windows-OverlayFilter Microsoft-Windows-Power-Meter-Polling Microsoft-Windows-ReFS Microsoft-Windows-ReFS-v1 Microsoft-Windows-Resource-Exhaustion-Detector Microsoft-Windows-ScmDisk0101 Microsoft-Windows-SDDC-Management Microsoft-Windows-Serial-ClassExtension Microsoft-Windows-ServerManager-ConfigureSMRemoting Microsoft-Windows-Servicing Microsoft-Windows-Setup Microsoft-Windows-SetupPlatform Microsoft-Windows-SPB-ClassExtension Microsoft-Windows-Subsys-SMSS Microsoft-Windows-TaskScheduler Microsoft-Windows-TerminalServices-LocalSessionManager Microsoft-Windows-TerminalServices-RemoteConnectionManager Microsoft-Windows-TerminalServices-SessionBroker-Client Microsoft-Windows-Time-Service Microsoft-Windows-TPM-WMI Microsoft-Windows-UserModePowerService Microsoft-Windows-UserPnp Microsoft-Windows-WindowsUpdateClient Microsoft-Windows-Wininit Microsoft-Windows-Winlogon mlx4_bus mouclass mouhid mrxsmb MSiSCSI MsLbfoProvider MTConfig Mup mvumis NdisImPlatform NdisImPlatformSysEvtProvider NdisWan ndiswanlegacy NetBIOS NetBT NetJoin Netlogon netvscvfpp Ntfs nvstor Parport partmgr percsas2i percsas3i Power PptpMiniport Print PrintFilterPipelineSvc Processor ql2300i ql40xx2i qlfcoei RasCfg Rasman RasSstp rdbss RemoteAccess rspndr SAM sbp2port SCardSvr Schannel scmbus scmdisk0101 sercx Serial sermouse Server Service Control Manager SiSRaid2 SiSRaid4 SMSvcHost 4.0.0.0 SNMPTRAP spaceport spbcx Srv stexstor storahci stornvme Tcpip Tcpip6 TCPMon TermService TermServJet TPM tsusbhub tunnel UASPStor UEFI UmRdpService usbehci usbser User32 VDS Basic Provider VDS Dynamic Provider VDS Virtual Disk Provider Virtual Disk Service vmci volmgr Volsnap vpci vsmraid VSTXRAID W32Time WacomPen wdf01000 wecsvc Win32k WinDefend WinHttpAutoProxySvc WinNat WinRM WMIxWDM Workstation  | 
| c:\windows\system32\winevt\logs\windows powershell.evtx | c:\windows\system32\winevt\logs\windows powershell.evtx | 20190918100732.787811-420 | C:\Windows\System32\Winevt\Logs\Windows PowerShell.evtx | OK | 18446744073709551615 | True | Win32_ComputerSystem | FOREST | False | Win32_NTEventlogFile | 20190918100732.787811-420 | False | Win32_FileSystem | NTFS | 20190918100732.787811-420 | 20250905043742.423198-420 | True | 1118208 | True | False | False | evtx File | c:\windows\system32\winevt\logs\window~1.evt | None | None | c: | \windows\system32\winevt\logs\ | Windows PowerShell | evtx | None | None | None | Windows PowerShell | 15728640 | 253 | WhenNeeded | 0 | Windows PowerShell PowerShell  |
```
#### Win32_NTLogEvent
```sh
WQL> SELECT * FROM Win32_NTLogEvent WHERE LogFile = "windows powershell" AND RecordNumber = 1
| RecordNumber | Logfile | EventIdentifier | EventCode | SourceName | Type | Category | CategoryString | TimeGenerated | TimeWritten | ComputerName | User | Message | InsertionStrings | Data | EventType | 
| 1 | Windows PowerShell | 600 | 600 | PowerShell | Information | 6 | Provider Lifecycle | 20190918170915.514729-000 | 20190918170915.514729-000 | WIN-TN63P6UFH7R | None | Provider "Registry" is Started. 

Details: 
        ProviderName=Registry
        NewProviderState=Started

        SequenceNumber=1

        HostName=ConsoleHost
        HostVersion=5.1.14393.206
        HostId=ceb02fed-7ead-4325-bf42-c7fd57395a06
        HostApplication=powershell
        EngineVersion=
        RunspaceId=
        PipelineId=
        CommandName=
        CommandType=
        ScriptName=
        CommandPath=
        CommandLine= | Registry Started         ProviderName=Registry
        NewProviderState=Started

        SequenceNumber=1

        HostName=ConsoleHost
        HostVersion=5.1.14393.206
        HostId=ceb02fed-7ead-4325-bf42-c7fd57395a06
        HostApplication=powershell
        EngineVersion=
        RunspaceId=
        PipelineId=
        CommandName=
        CommandType=
        ScriptName=
        CommandPath=
        CommandLine=  | None | 3 |
```
#### Win32_NTLogEventComputer
```sh
WQL> SELECT * FROM Win32_NTLogEventComputer WHERE Record = 'Win32_NTLogEvent.Logfile="Application",RecordNumber=2117'
| Computer | Record | 
| Win32_ComputerSystem.Name="FOREST" | Win32_NTLogEvent.Logfile="Application",RecordNumber=2117 |
```
#### Win32_NTLogEventLog
```sh
WQL> SELECT * FROM Win32_NTLogEventLog WHERE Record = 'Win32_NTLogEvent.Logfile="Windows Powershell",RecordNumber=1'
| Log | Record | 
| Win32_NTEventlogFile.Name="C:\\Windows\\System32\\Winevt\\Logs\\Windows PowerShell.evtx" | Win32_NTLogEvent.Logfile="Windows Powershell",RecordNumber=1 | 
```
#### Win32_NTLogEventUser
```sh
WQL> SELECT * FROM Win32_NTLogEventUser
| User | Record | 
| Win32_UserAccount.Domain="HTB",Name="Administrator" | Win32_NTLogEvent.Logfile="Application",RecordNumber=622 | 
| Win32_UserAccount.Domain="HTB",Name="Administrator" | Win32_NTLogEvent.Logfile="Application",RecordNumber=621 | 
| Win32_UserAccount.Domain="HTB",Name="Administrator" | Win32_NTLogEvent.Logfile="Application",RecordNumber=620 |
```


### Windows Product Activation
#### Win32_ComputerSystemWindowsProductActivationSetting
#### Win32_Proxy
#### Win32_WindowsProductActivation





## Performance Counter Classes
### Win32_Perf
```sh
WQL> SELECT * FROM Win32_Perf WHERE Name = "DefenderApiLogger"
| Name | Description | Caption | Frequency_PerfTime | Timestamp_PerfTime | Timestamp_Sys100NS | Frequency_Sys100NS | Frequency_Object | Timestamp_Object | BufferMemoryUsageNonPagedPool | BufferMemoryUsagePagedPool | EventsLoggedpersec | EventsLost | NumberofRealTimeConsumers | 
| DefenderApiLogger | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 131072 | 0 | 0 | 0 | 0 | 
| DefenderApiLogger | None | None | 2534301 | 35633925097 | 134016248737972461 | 10000000 | 0 | 0 | 131072 | 0 | 0 | 0 | 0 |
```
### Win32_PerfFormattedData
```sh
WQL> SELECT * FROM Win32_PerfFormattedData WHERE Name = "DefenderApiLogger"
| Name | Description | Caption | Frequency_PerfTime | Timestamp_PerfTime | Timestamp_Sys100NS | Frequency_Sys100NS | Frequency_Object | Timestamp_Object | BufferMemoryUsageNonPagedPool | BufferMemoryUsagePagedPool | EventsLoggedpersec | EventsLost | NumberofRealTimeConsumers | 
| DefenderApiLogger | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 131072 | 0 | 0 | 0 | 0 |
```





## WMI Service Management Classes
### WMI Configuration
#### Win32_MethodParameterClass


### WMI Management Classes
#### Win32_WMISetting
```sh
WQL> SELECT * FROM Win32_WMISetting
| SettingID | Caption | Description | InstallationDirectory | BuildVersion | MofSelfInstallDirectory | AutorecoverMofs | AutoStartWin9X | EnableAnonWin9xConnections | MaxLogFileSize | LoggingLevel | LoggingDirectory | DatabaseDirectory | DatabaseMaxSize | BackupInterval | BackupLastTime | ASPScriptEnabled | ASPScriptDefaultNamespace | EnableEvents | HighThresholdOnClientObjects | LowThresholdOnClientObjects | MaxWaitOnClientObjects | HighThresholdOnEvents | LowThresholdOnEvents | MaxWaitOnEvents | EnableStartupHeapPreallocation | LastStartupHeapPreallocation | 
| None | None | None | C:\Windows\system32\wbem | 14393.0 | None | %windir%\system32\wbem\cimwin32.mof %windir%\system32\wbem\ncprov.mof %windir%\system32\wbem\wmipcima.mof %windir%\system32\wbem\secrcw32.mof %windir%\system32\wbem\system.mof %windir%\system32\wbem\interop.mof %windir%\system32\wbem\wmi.mof %windir%\system32\wbem\wmi_tracing.mof %windir%\system32\wbem\scrcons.mof %windir%\system32\wbem\smtpcons.mof %windir%\system32\wbem\wbemcons.mof %windir%\system32\wbem\subscrpt.mof %windir%\system32\wbem\win32_printer.mof %windir%\system32\wbem\tcpip.mof %windir%\system32\wbem\ncsi.mof %windir%\system32\wbem\nlasvc.mof %windir%\system32\wbem\tspkg.mof %windir%\system32\wbem\services.mof %windir%\system32\wbem\scm.mof %windir%\system32\wbem\drvinst.mof %windir%\system32\wbem\umpnpmgr.mof %windir%\system32\wbem\mountmgr.mof %windir%\system32\wbem\cli.mof %windir%\system32\wbem\cliegaliases.mof %windir%\system32\wbem\policman.mof %windir%\system32\wbem\krnlprov.mof %windir%\system32\wbem\wmitimep.mof %windir%\system32\wbem\regevent.mof %windir%\system32\wbem\dsprov.mof %windir%\system32\wbem\wmipiprt.mof %windir%\system32\wbem\wmipjobj.mof %windir%\system32\wbem\ntevt.mof %windir%\system32\wbem\msi.mof %windir%\system32\wbem\wmipicmp.mof %windir%\system32\wbem\wmipdfs.mof %windir%\system32\wbem\wmipdskq.mof %windir%\system32\wbem\wmipsess.mof %windir%\system32\wbem\rsop.mof %windir%\system32\wbem\ppcrsopcompschema.mof %windir%\system32\wbem\ppcrsopuserschema.mof %windir%\system32\wbem\printfilterpipelinesvc.mof %windir%\system32\wbem\vss.mof %windir%\system32\wbem\vds.mof %windir%\system32\wbem\newdev.mof %windir%\system32\restartmanager.mof %windir%\system32\wbem\fundisc.mof %windir%\system32\wbem\fdwsd.mof %windir%\system32\wbem\umb.mof %windir%\system32\wbem\umbus.mof %windir%\system32\wbem\umpass.mof %windir%\system32\wbem\win32_tpm.mof %windir%\system32\wbem\sppwmi.mof %windir%\system32\wbem\schannel.mof %windir%\system32\wbem\ipsecsvc.mof %windir%\system32\wbem\polstore.mof %windir%\system32\wbem\winipsec.mof %windir%\system32\wbem\sstpsvc.mof %windir%\system32\wbem\wininit.mof %windir%\system32\wbem\cimdmtf.mof %windir%\system32\wbem\powermeterprovider.mof %windir%\system32\wbem\profileassociationprovider.mof %windir%\system32\wbem\lltdio.mof %windir%\system32\wbem\rspndr.mof %windir%\system32\wbem\lltdsvc.mof %windir%\system32\wbem\networkitemfactory.mof %windir%\system32\wbem\msv1_0.mof %windir%\system32\wbem\kerberos.mof %windir%\system32\wbem\wdigest.mof %windir%\system32\wbem\bcd.mof %windir%\system32\wbem\ntfs.mof %windir%\system32\wbem\setupapi.mof %windir%\system32\wbem\dimsjob.mof %windir%\system32\wbem\wsmauto.mof %windir%\system32\wbem\wsmagent.mof %windir%\system32\wbem\rdpshell.mof %windir%\system32\wbem\rdpinit.mof %windir%\system32\wbem\ipmiprv.mof %windir%\system32\wbem\ipmidtrc.mof %windir%\system32\wbem\ipmiptrc.mof %windir%\system32\wbem\microsoft-windows-remote-filesystem.mof %windir%\system32\wbem\whqlprov.mof %windir%\system32\wbem\wmiperfclass.mof %windir%\system32\wbem\wmiperfinst.mof %windir%\system32\wbem\scersop.mof %windir%\system32\wbem\winlogon.mof %windir%\system32\wbem\auditrsop.mof %windir%\system32\wbem\sdbus.mof %windir%\system32\wbem\msiscsi.mof %windir%\system32\wbem\iscsihba.mof %windir%\system32\wbem\iscsidsc.mof %windir%\system32\wbem\iscsiprf.mof %windir%\system32\wbem\iscsiwmiv2.mof %windir%\system32\wbem\hbaapi.mof %windir%\system32\wbem\dimsroam.mof %windir%\system32\wbem\eaimeapi.mof %windir%\system32\wbem\fdphost.mof %windir%\system32\wbem\pnpxassoc.mof %windir%\system32\wbem\nshipsec.mof %windir%\system32\wbem\polprocl.mof %windir%\system32\wbem\stortrace.mof %windir%\system32\wbem\classlog.mof %windir%\system32\wbem\tsallow.mof %windir%\system32\wbem\tscfgwmi.mof %windir%\system32\wbem\servercompprov.mof %windir%\system32\wbem\servicemodel.mof %windir%\system32\wbem\servicemodel35.mof %windir%\system32\wbem\netttcim.mof %windir%\system32\wbem\netdacim.mof %windir%\system32\wbem\netnccim.mof %windir%\system32\wbem\mgmtprovider.mof %windir%\system32\wbem\dscproxy.mof %windir%\system32\wbem\partmgr.mof %windir%\system32\wbem\smbwitnesswmiv2provider.mof %windir%\system32\wbem\wudfx.mof %windir%\system32\wbem\mpeval.mof %windir%\system32\wbem\qmgr.mof %windir%\system32\wbem\netadaptercim.mof %windir%\system32\wbem\netadaptercimtrace.mof %windir%\system32\wbem\eventtracingmanagement.mof %windir%\system32\wbem\schedprov.mof %windir%\system32\wbem\fwcfg.mof %windir%\system32\wbem\authfwcfg.mof %windir%\system32\wbem\win32_deviceguard.mof %windir%\system32\wbem\refs.mof %windir%\system32\wbem\neteventpacketcapture.mof %windir%\system32\wbem\msnetimplatform.mof %windir%\system32\wbem\netswitchteam.mof %windir%\system32\wbem\wsp_fs.mof %windir%\system32\wbem\userprofilewmiprovider.mof %windir%\system32\wbem\userprofileconfigurationwmiprovider.mof %windir%\system32\hypervisor.mof %windir%\system32\wbem\smbwmiv2.mof %windir%\system32\wbem\wfascim.mof %windir%\system32\wbem\wuaprovider.mof %windir%\system32\wbem\nlsvc.mof %windir%\system32\wbem\qoswmi.mof %windir%\system32\wbem\qoswmitrc.mof %windir%\system32\wbem\samsrv.mof %windir%\system32\wbem\mttmprov.mof %windir%\system32\wbem\wsp_health.mof %windir%\system32\wbem\netpeerdistcim.mof %windir%\system32\wbem\sum.mof %windir%\system32\wbem\wsp_sr.mof %windir%\system32\wbem\mistreamprov.mof %windir%\system32\wbem\dnsclientpsprovider.mof %windir%\system32\wbem\storagewmi.mof %windir%\system32\wbem\storagewmi_passthru.mof %windir%\system32\wbem\sdndiagnosticsprovider.mof %windir%\system32\wbem\dsctimer.mof %windir%\system32\wbem\netnat.mof %windir%\system32\wbem\servermanager.deploymentprovider.mof %windir%\system32\wbem\powerwmiprovider.mof %windir%\system32\wbem\nettcpip.mof %windir%\system32\psmodulediscoveryprovider.mof %windir%\system32\wbem\platid.mof %windir%\system32\wbem\refsv1.mof %windir%\system32\wbem\dnsclientcim.mof %windir%\system32\wbem\regprov.mof %ProgramFiles%\windows defender\protectionmanagement.mof %windir%\system32\wbem\silprovider.mof %windir%\system32\wbem\netprofm.mof %windir%\system32\wbem\nlmcim.mof %windir%\system32\wbem\ciwmi.mof %windir%\system32\wbem\dsccoreconfprov.mof %windir%\system32\wbem\npivwmi.mof %windir%\system32\wbem\wudfx02000.mof %windir%\system32\wbem\msdtcwmi.mof %windir%\system32\wbem\mpssvc.mof %windir%\system32\wbem\mpsdrv.mof %windir%\system32\wbem\firewallapi.mof %windir%\system32\wbem\wfapigp.mof %windir%\system32\wbem\dsccore.mof %windir%\system32\wbem\wdacwmiprov.mof %windir%\system32\wbem\lsasrv.mof %ProgramFiles%\windows defender\clientwmiinstall.mof %ProgramFiles%\windows defender\ammonitoringinstall.mof %ProgramFiles%\windows defender\amstatusinstall.mof %windir%\system32\wbem\pcsvdevice.mof %windir%\system32\wbem\wfp.mof %windir%\system32\wbem\mispace.mof %windir%\system32\wbem\wdf01000.mof %windir%\system32\wbem\ps_mmagent.mof %windir%\system32\wbem\printmanagementprovider.mof %windir%\system32\wbem\en-us\cimwin32.mfl %windir%\system32\wbem\en-us\wmipcima.mfl %windir%\system32\wbem\en-us\secrcw32.mfl %windir%\system32\wbem\en-us\ncprov.mfl %windir%\system32\wbem\en-us\system.mfl %windir%\system32\wbem\en-us\interop.mfl %windir%\system32\wbem\en-us\wmi.mfl %windir%\system32\wbem\en-us\subscrpt.mfl %windir%\system32\wbem\en-us\scrcons.mfl %windir%\system32\wbem\en-us\smtpcons.mfl %windir%\system32\wbem\en-us\wbemcons.mfl %windir%\system32\wbem\en-us\win32_printer.mfl %windir%\system32\wbem\en-us\cli.mfl %windir%\system32\wbem\en-us\cliegaliases.mfl %windir%\system32\wbem\en-us\policman.mfl %windir%\system32\wbem\en-us\krnlprov.mfl %windir%\system32\wbem\en-us\wmitimep.mfl %windir%\system32\wbem\en-us\regevent.mfl %windir%\system32\wbem\en-us\dsprov.mfl %windir%\system32\wbem\en-us\wmipiprt.mfl %windir%\system32\wbem\en-us\wmipjobj.mfl %windir%\system32\wbem\en-us\ntevt.mfl %windir%\system32\wbem\en-us\msi.mfl %windir%\system32\wbem\en-us\wmipicmp.mfl %windir%\system32\wbem\en-us\wmipdfs.mfl %windir%\system32\wbem\en-us\wmipdskq.mfl %windir%\system32\wbem\en-us\wmipsess.mfl %windir%\system32\wbem\en-us\rsop.mfl %windir%\system32\wbem\en-us\vss.mfl %windir%\system32\wbem\en-us\vds.mfl %windir%\system32\wbem\en-us\polprocl.mfl %windir%\system32\wbem\en-us\ipmiprv.mfl %windir%\system32\wbem\en-us\iscsiprf.mfl %windir%\system32\wbem\en-us\iscsidsc.mfl %windir%\system32\wbem\en-us\iscsiwmiv2.mfl %windir%\system32\wbem\en-us\whqlprov.mfl %windir%\system32\wbem\en-us\tscfgwmi.mfl %windir%\system32\wbem\en-us\wsp_sr.mfl %windir%\system32\wbem\en-us\netttcim.mfl %windir%\system32\wbem\en-us\netdacim.mfl %windir%\system32\wbem\en-us\netnccim.mfl %windir%\system32\wbem\en-us\sum.mfl %windir%\system32\wbem\en-us\printmanagementprovider.mfl %windir%\system32\wbem\en-us\netpeerdistcim.mfl %windir%\system32\wbem\en-us\dnsclientpsprovider.mfl %windir%\system32\wbem\en-us\sppwmi.mfl %windir%\system32\wbem\en-us\regprov.mfl %windir%\system32\wbem\en-us\netadaptercim.mfl %windir%\system32\wbem\en-us\netadaptercimtrace.mfl %windir%\system32\wbem\en-us\smbwmiv2.mfl %ProgramFiles%\windows defender\en-us\protectionmanagement.mfl %windir%\system32\wbem\en-us\schedprov.mfl %windir%\system32\wbem\en-us\mttmprov.mfl %windir%\system32\en-us\psmodulediscoveryprovider.mfl %windir%\system32\wbem\en-us\win32_deviceguard.mfl %windir%\system32\wbem\en-us\wdacwmiprov.mfl %windir%\system32\wbem\en-us\ciwmi.mfl %windir%\system32\wbem\en-us\mgmtprovider.mfl %windir%\system32\wbem\en-us\mistreamprov.mfl %windir%\system32\wbem\en-us\msdtcwmi.mfl %windir%\system32\wbem\en-us\nlmcim.mfl %windir%\system32\wbem\en-us\dsctimer.mfl %windir%\system32\wbem\en-us\mpeval.mfl %windir%\system32\wbem\en-us\wininit.mfl %windir%\system32\wbem\en-us\eventtracingmanagement.mfl %windir%\system32\wbem\en-us\wudfx02000.mfl %windir%\system32\wbem\en-us\wudfx.mfl %windir%\system32\wbem\en-us\sdndiagnosticsprovider.mfl %windir%\system32\wbem\en-us\mispace.mfl %windir%\system32\wbem\en-us\wsp_health.mfl %windir%\system32\wbem\en-us\neteventpacketcapture.mfl %windir%\system32\wbem\en-us\platid.mfl %windir%\system32\wbem\en-us\wfascim.mfl %windir%\system32\wbem\en-us\powerwmiprovider.mfl %windir%\system32\wbem\en-us\nettcpip.mfl %windir%\system32\wbem\en-us\qoswmi.mfl %windir%\system32\wbem\en-us\qoswmitrc.mfl %windir%\system32\wbem\en-us\netnat.mfl %windir%\system32\wbem\en-us\wsp_fs.mfl %windir%\system32\wbem\en-us\dscproxy.mfl %windir%\system32\en-us\restartmanager.mfl %windir%\system32\wbem\en-us\npivwmi.mfl %windir%\system32\wbem\en-us\winlogon.mfl %windir%\system32\wbem\en-us\msnetimplatform.mfl %windir%\system32\wbem\en-us\netswitchteam.mfl %windir%\system32\wbem\en-us\dsccoreconfprov.mfl %windir%\system32\wbem\en-us\userprofilewmiprovider.mfl %windir%\system32\wbem\en-us\userprofileconfigurationwmiprovider.mfl %windir%\system32\en-us\hypervisor.mfl %windir%\system32\wbem\en-us\pcsvdevice.mfl %windir%\system32\wbem\en-us\cimdmtf.mfl %windir%\system32\wbem\en-us\powermeterprovider.mfl %windir%\system32\wbem\en-us\profileassociationprovider.mfl %windir%\system32\wbem\en-us\storagewmi.mfl %windir%\system32\wbem\en-us\storagewmi_passthru.mfl %windir%\system32\wbem\en-us\servercompprov.mfl %windir%\system32\wbem\en-us\silprovider.mfl %windir%\system32\wbem\en-us\dsccore.mfl %windir%\system32\wbem\en-us\smbwitnesswmiv2provider.mfl %windir%\system32\wbem\en-us\hbaapi.mfl %windir%\system32\wbem\en-us\ps_mmagent.mfl %windir%\system32\wbem\en-us\tsallow.mfl %windir%\system32\wbem\en-us\servermanager.deploymentprovider.mfl %windir%\system32\wbem\tspkg.mof %windir%\system32\wbem\wsmauto.mof %windir%\system32\wbem\wsmagent.mof %windir%\system32\wbem\en-us\storagewmi.mfl %windir%\system32\wbem\en-us\storagewmi_passthru.mfl %windir%\system32\wbem\en-us\dsccore.mfl %windir%\system32\wbem\wsp_health.mof %windir%\system32\wbem\wsp_sr.mof %windir%\system32\wbem\wsp_fs.mof %windir%\system32\wbem\mispace.mof %windir%\system32\wbem\storagewmi.mof %windir%\system32\wbem\storagewmi_passthru.mof %windir%\system32\wbem\dsccore.mof C:\WINDOWS\SYSTEM32\WBEM\MSWMDM.MOF D:\WSC_CLEAN.MOF C:\WINDOWS\SYSTEM32\WBEM\KDCSVC.MOF C:\WINDOWS\SYSTEM32\WBEM\EN-US\REPLPROV.MFL C:\WINDOWS\SYSTEM32\REPLPROV.MOF C:\WINDOWS\SYSTEM32\WBEM\ADSTATUS\EN-US\TRUSTMON.MFL C:\WINDOWS\SYSTEM32\WBEM\ADSTATUS\TRUSTMON.MOF C:\WINDOWS\SYSTEM32\WBEM\DFSRWMIV2.MOF C:\WINDOWS\SYSTEM32\WBEM\DFSRPROVS.MOF C:\WINDOWS\SYSTEM32\WBEM\DFSNCIMPROV.MOF C:\WINDOWS\SYSTEM32\WBEM\EN-US\DFSNCIMPROV.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\DFSRPROVS.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\DFSRWMIV2.MFL C:\WINDOWS\SYSTEM32\WBEM\NTDSA.MOF C:\WINDOWS\SYSTEM32\WBEM\DNSETW.MOF C:\WINDOWS\SYSTEM32\WBEM\DNSPROV.MOF C:\WINDOWS\SYSTEM32\WBEM\EN-US\DNSETW.MFL C:\WINDOWS\SYSTEM32\WBEM\DNSSERVERPSPROVIDER.MOF C:\WINDOWS\SYSTEM32\WBEM\EN-US\DNSSERVERPSPROVIDER.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\DNSPROV.MFL C:\WINDOWS\SYSTEM32\WBEM\TSPKG.MOF C:\WINDOWS\SYSTEM32\WBEM\WSMAUTO.MOF C:\WINDOWS\SYSTEM32\WBEM\WSMAGENT.MOF C:\WINDOWS\SYSTEM32\WBEM\EN-US\SDNDIAGNOSTICSPROVIDER.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\STORAGEWMI.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\STORAGEWMI_PASSTHRU.MFL C:\WINDOWS\SYSTEM32\WBEM\EN-US\SDDCPROV.MFL C:\WINDOWS\SYSTEM32\WBEM\NETADAPTERCIM.MOF C:\WINDOWS\SYSTEM32\WBEM\NETADAPTERCIMTRACE.MOF C:\WINDOWS\SYSTEM32\WBEM\SDNDIAGNOSTICSPROVIDER.MOF C:\WINDOWS\SYSTEM32\WBEM\WSP_FS.MOF C:\WINDOWS\SYSTEM32\WBEM\NETTCPIP.MOF C:\WINDOWS\SYSTEM32\WBEM\WSP_HEALTH.MOF C:\WINDOWS\SYSTEM32\WBEM\SDDCPROV.MOF C:\WINDOWS\SYSTEM32\WBEM\WSP_SR.MOF C:\WINDOWS\SYSTEM32\WBEM\MISPACE.MOF C:\WINDOWS\SYSTEM32\WBEM\STORAGEWMI.MOF C:\WINDOWS\SYSTEM32\WBEM\STORAGEWMI_PASSTHRU.MOF C:\WINDOWS\SYSTEM32\WBEM\VMSTATSPROVIDER.MOF  | None | None | 65536 | 0 | C:\Windows\system32\wbem\Logs\ | C:\Windows\system32\wbem\repository | None | None | None | None | root\cimv2 | True | None | None | None | 20000000 | 10000000 | 2000 | False | None |
```
#### Win32_WMIElementSetting
```sh
WQL> SELECT * FROM Win32_WMIElementSetting
| Element | Setting | 
| Win32_Service="winmgmt" | Win32_WMISetting=@ |
```





# Win32_ClusterShare class





# Win32_OptionalFeature class
```sh
WQL> SELECT * FROM Win32_OptionalFeature
| Caption | Description | InstallDate | Name | Status | InstallState | 
| .NET Framework 4.6 Features | None | None | NetFx4ServerFeatures | None | 1 | 
| .NET Framework 4.6 | None | None | NetFx4 | None | 1 | 
| ASP.NET 4.6 | None | None | NetFx4Extended-ASPNET45 | None | 2 | 
| Windows PowerShell | None | None | MicrosoftWindowsPowerShellRoot | None | 1 | 
| Windows PowerShell | None | None | MicrosoftWindowsPowerShell | None | 1 | 
| Remote Access Management Tools | None | None | RemoteAccessMgmtTools | None | 2 | 
| Remote Access module for Windows PowerShell | None | None | RemoteAccessPowerShell | None | 2 | 
|  | None | None | WSS-Product-Package | None | 2 | 
| Active Directory PowerShell | None | None | ActiveDirectory-PowerShell | None | 1 | 
| Active Directory Domain Controller | None | None | DirectoryServices-DomainController | None | 1 | 
|  | None | None | HostGuardianService-Package | None | 2 | 
| Active Directory Administrative Center | None | None | DirectoryServices-AdministrativeCenter | None | 2 | 
| Remote Access | None | None | RemoteAccess | None | 2 | 
| Remote Access Server | None | None | RemoteAccessServer | None | 2 | 
| Ras Server Routing Protocols | None | None | RasRoutingProtocols | None | 2 | 
| Active Directory Federation Services Proxy | None | None | Web-Application-Proxy | None | 2 | 
| iSCSI Target Server Powershell | None | None | iSCSITargetServer-PowerShell | None | 2 | 
| Windows PowerShell 2.0 Engine | None | None | MicrosoftWindowsPowerShellV2 | None | 1 | 
| Windows PowerShell Web Access | None | None | WindowsPowerShellWebAccess | None | 2 | 
| Rights Management Services | None | None | RightsManagementServices-Role | None | 2 | 
| Rights Management Services | None | None | RightsManagementServices | None | 2 | 
| Federation support for Rights Management Services | None | None | RMS-Federation | None | 2 | 
|  | None | None | RightsManagementServices-AdminTools | None | 2 | 
| DataCenterBridging LLDP Tools | None | None | DataCenterBridging-LLDP-Tools | None | 2 | 
| Microsoft Windows ServerCore Foundational PowerShell Cmdlets | None | None | Server-Psh-Cmdlets | None | 1 | 
| PKIClient PowerShell Cmdlets | None | None | PKIClient-PSH-Cmdlets | None | 2 | 
| Key Distribution Service PowerShell Cmdlets | None | None | KeyDistributionService-PSH-Cmdlets | None | 1 | 
| TLS Session Ticket Key Commands | None | None | TlsSessionTicketKey-PSH-Cmdlets | None | 1 | 
| Trusted Platform Module Service PowerShell Cmdlets | None | None | Tpm-PSH-Cmdlets | None | 1 | 
| Internet Information Services | None | None | IIS-WebServerRole | None | 2 | 
| World Wide Web Services | None | None | IIS-WebServer | None | 2 | 
| Common HTTP Features | None | None | IIS-CommonHttpFeatures | None | 2 | 
| Security | None | None | IIS-Security | None | 2 | 
| Request Filtering | None | None | IIS-RequestFiltering | None | 2 | 
| Static Content | None | None | IIS-StaticContent | None | 2 | 
| Default Document | None | None | IIS-DefaultDocument | None | 2 | 
| Directory Browsing | None | None | IIS-DirectoryBrowsing | None | 2 | 
| HTTP Errors | None | None | IIS-HttpErrors | None | 2 | 
| HTTP Redirection | None | None | IIS-HttpRedirect | None | 2 | 
| WebDAV Publishing | None | None | IIS-WebDAV | None | 2 | 
| Application Development Features | None | None | IIS-ApplicationDevelopment | None | 2 | 
| WebSocket Protocol | None | None | IIS-WebSockets | None | 2 | 
| Application Initialization | None | None | IIS-ApplicationInit | None | 2 | 
| .NET Extensibility 3.5 | None | None | IIS-NetFxExtensibility | None | 2 | 
| .NET Extensibility 4.6 | None | None | IIS-NetFxExtensibility45 | None | 2 | 
| ISAPI Extensions | None | None | IIS-ISAPIExtensions | None | 2 | 
| ISAPI Filters | None | None | IIS-ISAPIFilter | None | 2 | 
| ASP.NET 3.5 | None | None | IIS-ASPNET | None | 2 | 
| ASP.NET 4.6 | None | None | IIS-ASPNET45 | None | 2 | 
| ASP | None | None | IIS-ASP | None | 2 | 
| CGI | None | None | IIS-CGI | None | 2 | 
| Server-Side Includes | None | None | IIS-ServerSideIncludes | None | 2 | 
| Health and Diagnostics | None | None | IIS-HealthAndDiagnostics | None | 2 | 
| HTTP Logging | None | None | IIS-HttpLogging | None | 2 | 
| Logging Tools | None | None | IIS-LoggingLibraries | None | 2 | 
| Request Monitor | None | None | IIS-RequestMonitor | None | 2 | 
| Tracing | None | None | IIS-HttpTracing | None | 2 | 
| Custom Logging | None | None | IIS-CustomLogging | None | 2 | 
| ODBC Logging | None | None | IIS-ODBCLogging | None | 2 | 
| Centralized SSL Certificate Support | None | None | IIS-CertProvider | None | 2 | 
| Basic Authentication | None | None | IIS-BasicAuthentication | None | 2 | 
| Windows Authentication | None | None | IIS-WindowsAuthentication | None | 2 | 
| Digest Authentication | None | None | IIS-DigestAuthentication | None | 2 | 
| Client Certificate Mapping Authentication | None | None | IIS-ClientCertificateMappingAuthentication | None | 2 | 
| IIS Client Certificate Mapping Authentication | None | None | IIS-IISCertificateMappingAuthentication | None | 2 | 
| URL Authorization | None | None | IIS-URLAuthorization | None | 2 | 
| IP Security | None | None | IIS-IPSecurity | None | 2 | 
| Performance Features | None | None | IIS-Performance | None | 2 | 
| Static Content Compression | None | None | IIS-HttpCompressionStatic | None | 2 | 
| Dynamic Content Compression | None | None | IIS-HttpCompressionDynamic | None | 2 | 
| Web Management Tools | None | None | IIS-WebServerManagementTools | None | 2 | 
| IIS Management Console | None | None | IIS-ManagementConsole | None | 3 | 
| IIS 6 Management Console | None | None | IIS-LegacySnapIn | None | 3 | 
| IIS Management Scripts and Tools | None | None | IIS-ManagementScriptingTools | None | 2 | 
| IIS Management Service | None | None | IIS-ManagementService | None | 2 | 
| IIS 6 Management Compatibility | None | None | IIS-IIS6ManagementCompatibility | None | 2 | 
| IIS Metabase and IIS 6 configuration compatibility | None | None | IIS-Metabase | None | 2 | 
| IIS 6 WMI Compatibility | None | None | IIS-WMICompatibility | None | 2 | 
| IIS 6 Scripting Tools | None | None | IIS-LegacyScripts | None | 2 | 
| FTP Server | None | None | IIS-FTPServer | None | 2 | 
| FTP Service | None | None | IIS-FTPSvc | None | 2 | 
| FTP Extensibility | None | None | IIS-FTPExtensibility | None | 2 | 
| Windows Process Activation Service | None | None | WAS-WindowsActivationService | None | 2 | 
| Process Model | None | None | WAS-ProcessModel | None | 2 | 
| .NET Environment 3.5 | None | None | WAS-NetFxEnvironment | None | 2 | 
| Configuration APIs | None | None | WAS-ConfigurationAPI | None | 2 | 
| Internet Information Services Hostable Web Core | None | None | IIS-HostableWebCore | None | 2 | 
| Message Queuing | None | None | MSMQ | None | 2 | 
| Message Queuing Services | None | None | MSMQ-Services | None | 2 | 
| Microsoft Message Queue (MSMQ) Server | None | None | MSMQ-Server | None | 2 | 
| MSMQ Triggers | None | None | MSMQ-Triggers | None | 2 | 
| MSMQ Active Directory Domain Services Integration | None | None | MSMQ-ADIntegration | None | 2 | 
| MSMQ HTTP Support | None | None | MSMQ-HTTP | None | 2 | 
| Multicasting Support | None | None | MSMQ-Multicast | None | 3 | 
| MSMQ DCOM Proxy | None | None | MSMQ-DCOMProxy | None | 2 | 
| MSMQ routing server | None | None | MSMQ-RoutingServer | None | 2 | 
| WCF Services | None | None | WCF-Services45 | None | 1 | 
| HTTP Activation | None | None | WCF-HTTP-Activation45 | None | 2 | 
| TCP Activation | None | None | WCF-TCP-Activation45 | None | 2 | 
| Named Pipe Activation | None | None | WCF-Pipe-Activation45 | None | 2 | 
| Message Queuing (MSMQ) Activation | None | None | WCF-MSMQ-Activation45 | None | 2 | 
| TCP Port Sharing | None | None | WCF-TCP-PortSharing45 | None | 1 | 
| Management OData IIS Extension | None | None | ManagementOdata | None | 2 | 
| Windows PowerShell Desired State Configuration Service | None | None | DSC-Service | None | 2 | 
| Active Directory Certificate Services | None | None | ADCertificateServicesRole | None | 2 | 
| Certificate Service | None | None | CertificateServices | None | 2 | 
| Online Revocation Services | None | None | OnlineRevocationServices | None | 2 | 
| Web Enrollment Services | None | None | WebEnrollmentServices | None | 2 | 
| Network Device Enrollment Services | None | None | NetworkDeviceEnrollmentServices | None | 2 | 
| Certificate Services Enrollment Policy Server | None | None | CertificateEnrollmentPolicyServer | None | 2 | 
| Certificate Services Enrollment Server | None | None | CertificateEnrollmentServer | None | 2 | 
| Active Directory Federation Services | None | None | IdentityServer-SecurityTokenService | None | 2 | 
| IPAM Server Feature | None | None | IPAMServerFeature | None | 2 | 
| Device Health Attestation | None | None | DeviceHealthAttestationService | None | 2 | 
| Background Intelligent Transfer Service (BITS) Server Extensions for File Upload | None | None | BITSExtensions-Upload | None | 3 | 
| Windows Communication Foundation HTTP Activation | None | None | WCF-HTTP-Activation | None | 2 | 
| Windows Communication Foundation Non-HTTP Activation | None | None | WCF-NonHTTP-Activation | None | 2 | 
| RPC over HTTP proxy | None | None | RPC-HTTP_Proxy | None | 2 | 
| SMTP Service Admin Pack | None | None | Smtpsvc-Admin-Update-Name | None | 3 | 
| SMTP Service | None | None | Smtpsvc-Service-Update-Name | None | 3 | 
| Remote Desktop Services Web Access | None | None | WebAccess | None | 3 | 
| Windows Server Update Services | None | None | UpdateServices | None | 2 | 
| WSUS Services | None | None | UpdateServices-Services | None | 2 | 
| SQL Server Connectivity | None | None | UpdateServices-Database | None | 2 | 
| WID Connectivity | None | None | UpdateServices-WidDatabase | None | 2 | 
| Windows Remote Management (WinRM) IIS Extension | None | None | Microsoft-Windows-Web-Services-for-Management-IIS-Extension | None | 2 | 
| Work Folders | None | None | WorkFolders-Server | None | 2 | 
| Windows Server Update Services Tools | None | None | UpdateServices-RSAT | None | 2 | 
| API and PowerShell cmdlets | None | None | UpdateServices-API | None | 2 | 
| Active Directory Lightweight Directory Services | None | None | DirectoryServices-ADAM | None | 2 | 
| FSRM Infrastructure | None | None | FSRM-Infrastructure | None | 2 | 
| Microsoft-Windows-FCI-Client-Package | None | None | Microsoft-Windows-FCI-Client-Package | None | 2 | 
| FSRM Infrastructure Services | None | None | FSRM-Infrastructure-Services | None | 2 | 
| IPAM Management Tools | None | None | IPAMClientFeature | None | 2 | 
| Microsoft Windows AuthManager | None | None | AuthManager | None | 2 | 
| Microsoft Windows ServerCore WOW64 | None | None | ServerCore-WOW64 | None | 1 | 
| Print and Document Services | None | None | Printing-Server-Foundation-Features | None | 2 | 
| Windows Print Server Role Settings | None | None | Printing-Server-Role | None | 2 | 
| LPD Print Service | None | None | Printing-LPDPrintService | None | 2 | 
| Windows Server Print Client | None | None | Printing-Client | None | 1 | 
| Windows Server Print Client Management UI | None | None | Printing-Client-Gui | None | 3 | 
| ServerCore East Asian IME WOW64 | None | None | ServerCore-EA-IME-WOW64 | None | 1 | 
|  | None | None | ServerManager-Core-RSAT | None | 1 | 
|  | None | None | ServerManager-Core-RSAT-Role-Tools | None | 1 | 
|  | None | None | ServerManager-Core-RSAT-Feature-Tools | None | 2 | 
| DHCP Server Tools | None | None | DHCPServer-Tools | None | 2 | 
|  | None | None | RSAT-AD-Tools-Feature | None | 1 | 
|  | None | None | RSAT-ADDS-Tools-Feature | None | 2 | 
| Active Directory Domain Controller Tools | None | None | DirectoryServices-DomainController-Tools | None | 2 | 
| Active Directory Lightweight Directory Services Tools | None | None | DirectoryServices-ADAM-Tools | None | 2 | 
| DNS Server Tools | None | None | DNS-Server-Tools | None | 2 | 
| Hyper-V | None | None | Microsoft-Hyper-V | None | 2 | 
| Hyper-V Offline | None | None | Microsoft-Hyper-V-Offline | None | 2 | 
| Hyper-V Online | None | None | Microsoft-Hyper-V-Online | None | 2 | 
|  | None | None | RSAT-Hyper-V-Tools-Feature | None | 2 | 
| Hyper-V Management Console | None | None | Microsoft-Hyper-V-Management-Clients | None | 3 | 
| Hyper-V PowerShell cmdlets | None | None | Microsoft-Hyper-V-Management-PowerShell | None | 2 | 
| VM Host Agent | None | None | VmHostAgent | None | 2 | 
| Remote Administration pack for Shielded VM Tools | None | None | ShieldedVMToolsAdminPack | None | 2 | 
| Storage Replica Module for Windows PowerShell | None | None | Storage-Replica-AdminPack | None | 2 | 
| WINS Server Tools | None | None | WINS-Server-Tools | None | 3 | 
| .NET Framework 3.5 Features | None | None | NetFx3ServerFeatures | None | 2 | 
| .NET Framework 3.5 (includes .NET 2.0 and 3.0) | None | None | NetFx3 | None | 2 | 
| Enhanced Storage | None | None | EnhancedStorage | None | 2 | 
| BitLocker Drive Encryption | None | None | BitLocker | None | 2 | 
|  | None | None | Bitlocker-Utilities | None | 2 | 
|  | None | None | Microsoft-Windows-GroupPolicy-ServerAdminTools-Update | None | 1 | 
| Failover Cluster FullServer | None | None | FailoverCluster-FullServer | None | 2 | 
| Windows Server Backup | None | None | WindowsServerBackup | None | 2 | 
| CCFFilter | None | None | CCFFilter | None | 2 | 
| Failover Clustering Tools | None | None | FailoverCluster-AdminPak | None | 2 | 
| Failover Cluster Module for Windows PowerShell | None | None | FailoverCluster-PowerShell | None | 2 | 
| Hardened Fabric Encryption Task | None | None | HardenedFabricEncryptionTask | None | 2 | 
| Services for NFS | None | None | ServicesForNFS-ServerAndClient | None | 2 | 
| Server for NFS | None | None | ServerForNFS-Infrastructure | None | 2 | 
| Client for NFS | None | None | ClientForNFS-Infrastructure | None | 2 | 
| Simple TCPIP services (i.e. echo, daytime etc) | None | None | SimpleTCP | None | 2 | 
| SMB Direct | None | None | SmbDirect | None | 1 | 
| Windows Defender Features | None | None | Windows-Defender-Features | None | 1 | 
| Windows Defender | None | None | Windows-Defender | None | 1 | 
| Data Deduplication | None | None | Dedup-Core | None | 2 | 
| DFS Namespace | None | None | DFSN-Server | None | 2 | 
| Windows DFS Replication Service | None | None | DFSR-Infrastructure-ServerEdition | None | 2 | 
| DHCP Server feature | None | None | DHCPServer | None | 2 | 
| DNS Server | None | None | DNS-Server-Full-Role | None | 1 | 
| Failover Cluster Automation Server | None | None | FailoverCluster-AutomationServer | None | 2 | 
| Failover Cluster Command Interface | None | None | FailoverCluster-CmdInterface | None | 2 | 
| Windows File Replication Service | None | None | FRS-Infrastructure | None | 2 | 
| File Server VSS Agent Service | None | None | FileServerVSSAgent | None | 2 | 
| Windows Internal Database | None | None | Windows-Internal-Database | None | 2 | 
| WINS Runtime | None | None | WINSRuntime | None | 2 | 
| iSCSI Target Server - Disk Providers | None | None | iSCSITargetStorageProviders | None | 2 | 
| iSCSI Target Server | None | None | iSCSITargetServer | None | 2 | 
| iSNS Server service | None | None | iSNS_Service | None | 2 | 
| Background Intelligent Transfer Service (BITS) | None | None | BITS | None | 2 | 
| BITS Compact Server | None | None | LightweightServer | None | 2 | 
| Microsoft MultipathIo | None | None | MultipathIo | None | 2 | 
| MultiPoint Services | None | None | MultiPoint-Role | None | 2 | 
| MultiPoint Connector | None | None | MultiPoint-Connector | None | 2 | 
| MultiPoint Connector Services | None | None | MultiPoint-Connector-Services | None | 2 | 
| MultiPoint Manager and MultiPoint Dashboard | None | None | MultiPoint-Tools | None | 2 | 
| Network Load Balancing | None | None | NetworkLoadBalancingFullServer | None | 2 | 
| Containers | None | None | Containers | None | 2 | 
|  | None | None | PeerDist | None | 2 | 
| Peer Name Resolution Protocol(PNRP) | None | None | P2P-PnrpOnly | None | 2 | 
| Microsoft Print to PDF | None | None | Printing-PrintToPDFServices-Features | None | 1 | 
| XPS Services | None | None | Printing-XPSServices-Features | None | 1 | 
| QWAVE component | None | None | QWAVE | None | 2 | 
| Remote Differential Compression API Support | None | None | MSRDC-Infrastructure | None | 2 | 
| ResumeKeyFilter | None | None | ResumeKeyFilter | None | 2 | 
| ServerCore East Asian IME | None | None | ServerCore-EA-IME | None | 1 | 
| Data Center Bridging | None | None | DataCenterBridging | None | 2 | 
| I/O Quality of Service | None | None | DiskIo-QoS | None | 2 | 
| Media Foundation | None | None | ServerMediaFoundation | None | 2 | 
| Server Migration Tools | None | None | ServerMigration | None | 2 | 
| SMBHashGeneration | None | None | SMBHashGeneration | None | 2 | 
| SmbWitness | None | None | SmbWitness | None | 2 | 
| Simple Network Management Protocol (SNMP) for Server Core | None | None | SNMP | None | 2 | 
| WMI SNMP Provider | None | None | WMISnmpProvider | None | 2 | 
| Windows Standards-Based Storage Management | None | None | WindowsStorageManagementService | None | 2 | 
| Telnet Client | None | None | TelnetClient | None | 2 | 
| Remote Desktop Services | None | None | Remote-Desktop-Services | None | 2 | 
| Remote Desktop Services Session Directory Server | None | None | SessionDirectory | None | 2 | 
| Remote Desktop Services Session Broker Tools Admin Pack | None | None | SBMgr-UI | None | 2 | 
| Terminal Services Licensing | None | None | Licensing | None | 2 | 
| Volume Activation Services | None | None | VolumeActivation-Full-Role | None | 2 | 
| SMB 1.0/CIFS File Sharing Support | None | None | SMB1Protocol | None | 1 | 
| SMB Bandwidth Limit | None | None | SMBBW | None | 2 | 
| Microsoft-Windows-BootEvent-Collector-Opt-Package | None | None | SetupAndBootEventCollection | None | 2 | 
| VM Shielding Tools for Fabric Management | None | None | FabricShieldedTools | None | 2 | 
|  | None | None | FileAndStorage-Services | None | 1 | 
|  | None | None | Storage-Services | None | 1 | 
|  | None | None | File-Services | None | 1 | 
| File Server Role | None | None | CoreFileServer | None | 1 | 
| Server Core Drivers | None | None | ServerCore-Drivers-General | None | 1 | 
| Server Core WOW64 Drivers | None | None | ServerCore-Drivers-General-WOW64 | None | 1 |
```





# Win32_PnPDeviceProperty
