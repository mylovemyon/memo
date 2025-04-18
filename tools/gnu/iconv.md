## Usage
```
Usage: iconv [OPTION...] [FILE...]
Convert encoding of given files from one encoding to another.

 Input/Output format specification:
  -f, --from-code=NAME       encoding of original text
  -t, --to-code=NAME         encoding for output

 Information:
  -l, --list                 list all known coded character sets

 Output control:
  -c                         omit invalid characters from output
  -o, --output=FILE          output file
  -s, --silent               suppress warnings
      --verbose              print progress information

  -?, --help                 Give this help list
      --usage                Give a short usage message
  -V, --version              Print program version

Mandatory or optional arguments to long options are also mandatory or optional
for any corresponding short options.

For bug reporting instructions, please see:
<http://www.debian.org/Bugs/>.
```


## code
```
Completing code set
437                     CP950                   CSIBM866                CSKOI8R                 GREEKCCITT              IBM920                  ISO_8859-2              ISO-IR-148              OSF1002011C           
500                     CP1004                  CSIBM868                CSKSC5636               HEBREW                  IBM921                  ISO8859-2               ISO-IR-150              OSF1002011D           
500V1                   CP1008                  CSIBM869                CSMACINTOSH             HP-GREEK8               IBM922                  ISO_8859-2:1987         ISO-IR-151              OSF1002035D           
850                     CP1025                  CSIBM870                CSN_369103              HPGREEK8                IBM930                  ISO-8859-3              ISO-IR-153              OSF1002035E           
851                     CP1026                  CSIBM871                CSNATSDANO              HP-ROMAN8               IBM932                  ISO_8859-3              ISO-IR-155              OSF1002035F           
852                     CP1046                  CSIBM880                CSNATSSEFI              HPROMAN8                IBM933                  ISO8859-3               ISO-IR-156              OSF1002036B           
855                     CP1047                  CSIBM891                CSPC8CODEPAGE437        HP-ROMAN9               IBM935                  ISO_8859-3:1988         ISO-IR-157              OSF1002037B           
856                     CP1070                  CSIBM901                CSPC775BALTIC           HPROMAN9                IBM937                  ISO-8859-4              ISO-IR-166              OSF05010001           
857                     CP1079                  CSIBM902                CSPC850MULTILINGUAL     HP-THAI8                IBM939                  ISO_8859-4              ISO-IR-179              OSF10010001           
858                     CP1081                  CSIBM903                CSPC858MULTILINGUAL     HPTHAI8                 IBM943                  ISO8859-4               ISO-IR-193              OSF10010004           
860                     CP1084                  CSIBM904                CSPC862LATINHEBREW      HP-TURKISH8             IBM1004                 ISO_8859-4:1988         ISO-IR-197              OSF10010006           
861                     CP1089                  CSIBM905                CSPCP852                HPTURKISH8              IBM1008                 ISO-8859-5              ISO-IR-199              OSF10020025           
862                     CP1097                  CSIBM918                CSSHIFTJIS              HU                      IBM1025                 ISO_8859-5              ISO-IR-203              OSF10020111           
863                     CP1112                  CSIBM921                CSUCS4                  IBM037                  IBM1026                 ISO8859-5               ISO-IR-209              OSF10020115           
864                     CP1122                  CSIBM922                CSUNICODE               IBM038                  IBM1046                 ISO_8859-5:1988         ISO-IR-226              OSF10020116           
865                     CP1123                  CSIBM930                CSWINDOWS31J            IBM-803                 IBM1047                 ISO-8859-6              ISO/TR_11548-1/         OSF10020118           
866                     CP1124                  CSIBM932                CUBA                    IBM-856                 IBM1089                 ISO_8859-6              IT                      OSF10020122           
866NAV                  CP1125                  CSIBM933                CWI                     IBM-901                 IBM1097                 ISO8859-6               JIS_C6220-1969-RO       OSF10020129           
869                     CP1129                  CSIBM935                CWI-2                   IBM-902                 IBM1112                 ISO_8859-6:1987         JIS_C6229-1984-B        OSF10020352           
874                     CP1130                  CSIBM937                CYRILLIC                IBM-921                 IBM1122                 ISO-8859-7              JIS_C62201969RO         OSF10020354           
904                     CP1132                  CSIBM939                DE                      IBM-922                 IBM1123                 ISO_8859-7              JIS_C62291984B          OSF10020357           
1026                    CP1133                  CSIBM943                DEC                     IBM-930                 IBM1124                 ISO8859-7               JOHAB                   OSF10020359           
1046                    CP1137                  CSIBM1008               DEC-MCS                 IBM-932                 IBM1129                 ISO_8859-7:1987         JP                      OSF10020360           
1047                    CP1140                  CSIBM1025               DECMCS                  IBM-933                 IBM1130                 ISO_8859-7:2003         JP-OCR-B                OSF10020364           
8859_1                  CP1141                  CSIBM1026               DIN_66003               IBM-935                 IBM1132                 ISO-8859-8              JS                      OSF10020365           
8859_2                  CP1142                  CSIBM1097               DK                      IBM-937                 IBM1133                 ISO_8859-8              JUS_I.B1.002            OSF10020366           
8859_3                  CP1143                  CSIBM1112               DS_2089                 IBM-939                 IBM1137                 ISO8859-8               KOI-7                   OSF10020367           
8859_4                  CP1144                  CSIBM1122               DS2089                  IBM-943                 IBM1140                 ISO88598                KOI-8                   OSF10020370           
8859_5                  CP1145                  CSIBM1123               E13B                    IBM-1008                IBM1141                 ISO_8859-8:1988         KOI8                    OSF10020387           
8859_6                  CP1146                  CSIBM1124               EBCDIC-AT-DE            IBM-1025                IBM1142                 ISO-8859-9              KOI8-R                  OSF10020388           
8859_7                  CP1147                  CSIBM1129               EBCDICATDE              IBM-1046                IBM1143                 ISO_8859-9              KOI8R                   OSF10020396           
8859_8                  CP1148                  CSIBM1130               EBCDIC-AT-DE-A          IBM-1047                IBM1144                 ISO8859-9               KOI8-RU                 OSF10020402           
8859_9                  CP1149                  CSIBM1132               EBCDICATDEA             IBM-1097                IBM1145                 ISO88599                KOI8-T                  OSF10020417           
10646-1:1993            CP1153                  CSIBM1133               EBCDIC-BE               IBM-1112                IBM1146                 ISO_8859-9:1989         KOI8-U                  PT                    
10646-1:1993/UCS4/      CP1154                  CSIBM1137               EBCDIC-BR               IBM-1122                IBM1147                 ISO88599E               KOI8U                   PT2                   
ANSI_X3.4               CP1155                  CSIBM1140               EBCDIC-CA-FR            IBM-1123                IBM1148                 ISO885910               KSC5636                 PT154                 
ANSI_X3.4-1968          CP1156                  CSIBM1141               EBCDICCAFR              IBM-1124                IBM1149                 ISO885911               L1                      R8                    
ANSI_X3.4-1986          CP1157                  CSIBM1142               EBCDIC-CP-AR1           IBM-1129                IBM1153                 ISO885913               L2                      R9                    
ANSI_X3.110             CP1158                  CSIBM1143               EBCDIC-CP-AR2           IBM-1130                IBM1154                 ISO885914               L3                      RK1048                
ANSI_X3.110-1983        CP1160                  CSIBM1144               EBCDIC-CP-BE            IBM-1132                IBM1155                 ISO885915               L4                      ROMAN8                
ARABIC                  CP1161                  CSIBM1145               EBCDIC-CP-CA            IBM-1133                IBM1156                 ISO885916               L5                      ROMAN9                
ARABIC7                 CP1162                  CSIBM1146               EBCDIC-CP-CH            IBM-1137                IBM1157                 ISO-8859-9E             L6                      RUSCII                
ARMSCII-8               CP1163                  CSIBM1147               EBCDIC-CP-DK            IBM-1140                IBM1158                 ISO-8859-10             L7                      SE                    
ARMSCII8                CP1164                  CSIBM1148               EBCDIC-CP-ES            IBM-1141                IBM1160                 ISO-8859-11             L8                      SE2                   
ASCII                   CP1166                  CSIBM1149               EBCDIC-CP-FI            IBM-1142                IBM1161                 ISO-8859-13             L10                     SEN_850200_B          
ASMO_449                CP1167                  CSIBM1153               EBCDIC-CP-FR            IBM-1143                IBM1162                 ISO-8859-14             LATIN1                  SEN_850200_C          
ASMO-708                CP1250                  CSIBM1154               EBCDIC-CP-GB            IBM-1144                IBM1163                 ISO-8859-15             LATIN2                  SHIFT-JIS             
BALTIC                  CP1251                  CSIBM1155               EBCDIC-CP-GR            IBM-1145                IBM1164                 ISO-8859-16             LATIN3                  SHIFT_JIS             
BIG-5                   CP1252                  CSIBM1156               EBCDIC-CP-HE            IBM-1146                IBM1166                 ISO-10646               LATIN4                  SHIFT_JISX0213        
BIG5                    CP1253                  CSIBM1157               EBCDIC-CP-IS            IBM-1147                IBM1167                 ISO-10646/UCS2/         LATIN5                  SHIFTJISX0213         
BIG5-HKSCS              CP1254                  CSIBM1158               EBCDIC-CP-IT            IBM-1148                IBM1364                 ISO-10646/UCS4/         LATIN6                  SJIS                  
BIG5HKSCS               CP1255                  CSIBM1160               EBCDIC-CP-NL            IBM-1149                IBM1371                 ISO-10646/UTF-8/        LATIN7                  SJIS-OPEN             
BIG-FIVE                CP1256                  CSIBM1161               EBCDIC-CP-NO            IBM-1153                IBM1388                 ISO-10646/UTF8/         LATIN8                  SJIS-WIN              
BIGFIVE                 CP1257                  CSIBM1163               EBCDIC-CP-ROECE         IBM-1154                IBM1390                 ISO_8859-9E             LATIN-9                 SS636127              
BRF                     CP1258                  CSIBM1164               EBCDIC-CP-SE            IBM-1155                IBM1399                 ISO_8859-10             LATIN9                  STRK1048-2002         
BS_4730                 CP1282                  CSIBM1166               EBCDIC-CP-TR            IBM-1156                IBM4517                 ISO_8859-10:1992        LATIN10                 ST_SEV_358-88         
CA                      CP1361                  CSIBM1167               EBCDIC-CP-US            IBM-1157                IBM4899                 ISO_8859-14             LATIN-GREEK             T.61                  
CN                      CP1364                  CSIBM1364               EBCDIC-CP-WT            IBM-1158                IBM4909                 ISO_8859-14:1998        LATINGREEK              T.61-8BIT             
CN-BIG5                 CP1371                  CSIBM1371               EBCDIC-CP-YU            IBM-1160                IBM4971                 ISO_8859-15             LATIN-GREEK-1           T.618BIT              
CN-GB                   CP1388                  CSIBM1388               EBCDIC-CYRILLIC         IBM-1161                IBM5347                 ISO_8859-15:1998        LATINGREEK1             TCVN                  
CP037                   CP1390                  CSIBM1390               EBCDIC-DK-NO            IBM-1162                IBM9030                 ISO_8859-16             MAC                     TCVN-5712             
CP038                   CP1399                  CSIBM1399               EBCDICDKNO              IBM-1163                IBM9066                 ISO_8859-16:2001        MAC-CENTRALEUROPE       TCVN5712-1            
CP273                   CP4517                  CSIBM4517               EBCDIC-DK-NO-A          IBM-1164                IBM-9448                ISO8859-9E              MAC-CYRILLIC            TCVN5712-1:1993       
CP274                   CP4899                  CSIBM4899               EBCDICDKNOA             IBM-1166                IBM-12712               ISO8859-10              MACCYRILLIC             THAI8                 
CP275                   CP4909                  CSIBM4909               EBCDIC-ES               IBM-1167                IBM-16804               ISO8859-11              MACINTOSH               TIS-620               
CP278                   CP4971                  CSIBM4971               EBCDICES                IBM-1364                IBM9448                 ISO8859-13              MAC-IS                  TIS620                
CP280                   CP5347                  CSIBM5347               EBCDIC-ES-A             IBM-1371                IBM12712                ISO8859-14              MACIS                   TIS620-0              
CP281                   CP9030                  CSIBM9030               EBCDICESA               IBM-1388                IBM16804                ISO8859-15              MAC-SAMI                TIS620.2529-1         
CP282                   CP9066                  CSIBM9066               EBCDIC-ES-S             IBM-1390                IEC_P27-1               ISO8859-16              MAC-UK                  TIS620.2533-0         
CP284                   CP9448                  CSIBM9448               EBCDICESS               IBM-1399                IEC_P271                ISO11548-1              MACUK                   TS-5881               
CP285                   CP10007                 CSIBM12712              EBCDIC-FI-SE            IBM256                  INIS                    ISO88591                MACUKRAINIAN            TSCII                 
CP290                   CP12712                 CSIBM16804              EBCDICFISE              IBM273                  INIS-8                  ISO88592                MIK                     TURKISH8              
CP297                   CP16804                 CSIBM11621162           EBCDIC-FI-SE-A          IBM274                  INIS8                   ISO88593                MS932                   UCS-2                 
CP367                   CP-AR                   CSISO4UNITEDKINGDOM     EBCDICFISEA             IBM275                  INIS-CYRILLIC           ISO88594                MS936                   UCS2                  
CP420                   CP-GR                   CSISO10SWEDISH          EBCDIC-FR               IBM277                  INISCYRILLIC            ISO88595                MS-ANSI                 UCS-2BE               
CP423                   CP-HU                   CSISO11SWEDISHFORNAMES  EBCDICFR                IBM278                  ISIRI-3342              ISO88596                MS-ARAB                 UCS-2LE               
CP424                   CPIBM861                CSISO14JISC6220RO       EBCDIC-GREEK            IBM280                  ISIRI3342               ISO88597                MSCP949                 UCS-4                 
CP437                   CSA7-1                  CSISO15ITALIAN          EBCDIC-INT              IBM281                  ISO-2022-CN             ISO_9036                MSCP1361                UCS4                  
CP500                   CSA7-2                  CSISO16PORTUGESE        EBCDIC-INT1             IBM284                  ISO-2022-CN-EXT         ISO_10367-BOX           MS-CYRL                 UCS-4BE               
CP737                   CSASCII                 CSISO17SPANISH          EBCDIC-IS-FRISS         IBM285                  ISO-2022-JP             ISO_10367BOX            MS-EE                   UCS-4LE               
CP770                   CSA_T500                CSISO18GREEK7OLD        EBCDICISFRISS           IBM290                  ISO-2022-JP-2           ISO_11548-1             MS-GREEK                UHC                   
CP771                   CSA_T500-1983           CSISO19LATINGREEK       EBCDIC-IT               IBM297                  ISO-2022-JP-3           ISO_69372               MS-HEBR                 UJIS                  
CP772                   CSA_Z243.4-1985-1       CSISO21GERMAN           EBCDICIT                IBM367                  ISO-2022-KR             ISO-CELTIC              MS_KANJI                UK                    
CP773                   CSA_Z243.4-1985-2       CSISO25FRENCH           EBCDIC-JP-E             IBM420                  ISO646-CA               ISO-IR-4                MS-MAC-CYRILLIC         UNICODE               
CP774                   CSA_Z243.419851         CSISO27LATINGREEK1      EBCDIC-JP-KANA          IBM423                  ISO646-CA2              ISO-IR-6                MSMACCYRILLIC           UNICODEBIG            
CP775                   CSA_Z243.419852         CSISO49INIS             EBCDIC-PT               IBM424                  ISO646-CN               ISO-IR-8-1              MS-TURK                 UNICODELITTLE         
CP803                   CSDECMCS                CSISO50INIS8            EBCDICPT                IBM437                  ISO646-CU               ISO-IR-9-1              MSZ_7795.3              US                    
CP813                   CSEBCDICATDE            CSISO51INISCYRILLIC     EBCDIC-UK               IBM-4517                ISO646-DE               ISO-IR-10               NAPLPS                  US-ASCII              
CP819                   CSEBCDICATDEA           CSISO58GB1988           EBCDICUK                IBM-4899                ISO646-DK               ISO-IR-11               NATS-DANO               UTF16BE               
CP850                   CSEBCDICCAFR            CSISO60DANISHNORWEGIAN  EBCDIC-US               IBM-4909                ISO646-ES               ISO-IR-14               NATSDANO                UTF16LE               
CP851                   CSEBCDICDKNO            CSISO60NORWEGIAN1       EBCDICUS                IBM-4971                ISO646-ES2              ISO-IR-15               NATS-SEFI               UTF32                 
CP852                   CSEBCDICDKNOA           CSISO61NORWEGIAN2       ECMA-114                IBM500                  ISO646-FI               ISO-IR-16               NATSSEFI                UTF32BE               
CP855                   CSEBCDICES              CSISO69FRENCH           ECMA-118                IBM-5347                ISO646-FR               ISO-IR-17               NC_NC00-10              UTF-7                 
CP856                   CSEBCDICESA             CSISO84PORTUGUESE2      ECMA-128                IBM775                  ISO646-FR1              ISO-IR-18               NC_NC00-10:81           UTF-7-IMAP            
CP857                   CSEBCDICESS             CSISO85SPANISH2         ECMA-CYRILLIC           IBM803                  ISO646-GB               ISO-IR-19               NC_NC0010               UTF-8                 
CP858                   CSEBCDICFISE            CSISO86HUNGARIAN        ECMACYRILLIC            IBM813                  ISO646-HU               ISO-IR-21               NF_Z_62-010             UTF-16                
CP860                   CSEBCDICFISEA           CSISO88GREEK7           ELOT_928                IBM819                  ISO_646.IRV:1991        ISO-IR-25               NF_Z_62-010_\(1973\)    UTF-16BE              
CP861                   CSEBCDICFR              CSISO89ASMO449          ES                      IBM848                  ISO_2033                ISO-IR-27               NF_Z_62-010_1973        UTF-16LE              
CP862                   CSEBCDICIT              CSISO90                 ES2                     IBM850                  ISO_2033-1983           ISO-IR-37               NF_Z_62010              UTF-32                
CP863                   CSEBCDICPT              CSISO92JISC62991984B    EUC-CN                  IBM851                  ISO_5427                ISO-IR-49               NF_Z_62010_1973         UTF-32BE              
CP864                   CSEBCDICUK              CSISO99NAPLPS           EUCCN                   IBM852                  ISO_5427:1981           ISO-IR-50               NO                      UTF-32LE              
CP865                   CSEBCDICUS              CSISO103T618BIT         EUC-JISX0213            IBM855                  ISO_5427-EXT            ISO-IR-51               NO2                     UTF7                  
CP866                   CSEUCKR                 CSISO111ECMACYRILLIC    EUC-JP                  IBM856                  ISO_5427EXT             ISO-IR-54               NS_4551-1               UTF8                  
CP866NAV                CSEUCPKDFMTJAPANESE     CSISO121CANADIAN1       EUCJP                   IBM857                  ISO_5428                ISO-IR-55               NS_4551-2               UTF16                 
CP868                   CSGB2312                CSISO122CANADIAN2       EUC-JP-MS               IBM858                  ISO_5428:1980           ISO-IR-57               NS_45511                UTF32LE               
CP869                   CSHPROMAN8              CSISO139CSN369103       EUCJP-MS                IBM860                  ISO646-IT               ISO-IR-60               NS_45512                VISCII                
CP870                   CSIBM037                CSISO141JUSIB1002       EUCJP-OPEN              IBM861                  ISO646-JP               ISO-IR-61               OS2LATIN1               WCHAR_T               
CP871                   CSIBM038                CSISO143IECP271         EUCJP-WIN               IBM862                  ISO646-JP-OCR-B         ISO-IR-69               OSF0001000A             WINBALTRIM            
CP874                   CSIBM273                CSISO150                EUC-KR                  IBM863                  ISO646-KR               ISO-IR-84               OSF0004000A             WINDOWS-31J           
CP875                   CSIBM274                CSISO150GREEKCCITT      EUCKR                   IBM864                  ISO646-NO               ISO-IR-85               OSF0005000A             WINDOWS-874           
CP880                   CSIBM275                CSISO151CUBA            EUC-TW                  IBM865                  ISO646-NO2              ISO-IR-86               OSF00010001             WINDOWS-936           
CP891                   CSIBM277                CSISO153GOST1976874     EUCTW                   IBM866                  ISO646-PT               ISO-IR-88               OSF00010002             WINDOWS-1250          
CP901                   CSIBM278                CSISO646DANISH          FI                      IBM866NAV               ISO646-PT2              ISO-IR-89               OSF00010003             WINDOWS-1251          
CP902                   CSIBM280                CSISO2022CN             FR                      IBM868                  ISO646-SE               ISO-IR-90               OSF00010004             WINDOWS-1252          
CP903                   CSIBM281                CSISO2022JP             GB                      IBM869                  ISO646-SE2              ISO-IR-92               OSF00010005             WINDOWS-1253          
CP904                   CSIBM284                CSISO2022JP2            GB_198880               IBM870                  ISO646-US               ISO-IR-98               OSF00010006             WINDOWS-1254          
CP905                   CSIBM285                CSISO2022KR             GB2312                  IBM871                  ISO646-YU               ISO-IR-99               OSF00010007             WINDOWS-1255          
CP912                   CSIBM290                CSISO2033               GB13000                 IBM874                  ISO2022CN               ISO-IR-100              OSF00010008             WINDOWS-1256          
CP915                   CSIBM297                CSISO5427CYRILLIC       GB18030                 IBM875                  ISO2022CNEXT            ISO-IR-101              OSF00010009             WINDOWS-1257          
CP916                   CSIBM420                CSISO5427CYRILLIC1981   GB_1988-80              IBM880                  ISO2022JP               ISO-IR-103              OSF00010020             WINDOWS-1258          
CP918                   CSIBM423                CSISO5428GREEK          GBK                     IBM891                  ISO2022JP2              ISO-IR-109              OSF00010100             WIN-SAMI-2            
CP920                   CSIBM424                CSISO10367BOX           GEORGIAN-ACADEMY        IBM901                  ISO2022KR               ISO-IR-110              OSF00010101             WINSAMI2              
CP921                   CSIBM500                CSISOLATIN1             GEORGIAN-PS             IBM902                  ISO_6937                ISO-IR-111              OSF00010102             WS2                   
CP922                   CSIBM803                CSISOLATIN2             GOST_19768              IBM903                  ISO6937                 ISO-IR-121              OSF00010104             YU                    
CP930                   CSIBM851                CSISOLATIN3             GOST_19768-74           IBM-9030                ISO_6937:1992           ISO-IR-122              OSF00010105                                   
CP932                   CSIBM855                CSISOLATIN4             GOST_1976874            IBM904                  ISO_6937-2              ISO-IR-126              OSF00010106                                   
CP933                   CSIBM856                CSISOLATIN5             GREEK                   IBM905                  ISO_6937-2:1983         ISO-IR-127              OSF00030010                                   
CP935                   CSIBM857                CSISOLATIN6             GREEK7                  IBM-9066                ISO-8859-1              ISO-IR-138              OSF100201A4                                   
CP936                   CSIBM860                CSISOLATINARABIC        GREEK7-OLD              IBM912                  ISO_8859-1              ISO-IR-139              OSF100201A8                                   
CP937                   CSIBM863                CSISOLATINCYRILLIC      GREEK7OLD               IBM915                  ISO8859-1               ISO-IR-141              OSF100201B5                                   
CP939                   CSIBM864                CSISOLATINGREEK         GREEK8                  IBM916                  ISO_8859-1:1987         ISO-IR-143              OSF100201F4                                   
CP949                   CSIBM865                CSISOLATINHEBREW        GREEK-CCITT             IBM918                  ISO-8859-2              ISO-IR-144              OSF100203B5
```
