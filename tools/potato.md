https://jlajara.gitlab.io/Potatoes_Windows_Privesc  
https://hideandsec.sh/books/windows-sNL/page/in-the-potato-family-i-want-them-all

## Rotten Potato
https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/

- [RottenPotato](https://github.com/foxglovesec/RottenPotato/blob/master/README.md)  
  .Net Framework 4.0.30319が必要
- [RottenPotatoNG](https://github.com/breenmachine/RottenPotatoNG)  
  Metasploit用っぽい


## Juicy Potato
https://github.com/ohpe/juicy-potato

GitHubのReleaseでは、x64のEXEしかないもよう  
VisualStudioでx86用にコンパイルするとDLLが作成されるのでプロパティを設定する  
Projectのプロパティの「リンカ」「システム」「サブシステム」を「WINDOWS」から「CONSOLE」

```
JuicyPotato v0.1 

Mandatory args: 
-t createprocess call: <t> CreateProcessWithTokenW, <u> CreateProcessAsUser, <*> try both
-p <program>: program to launch
-l <port>: COM server listen port


Optional args: 
-m <ip>: COM server listen address (default 127.0.0.1)
-a <argument>: command line argument to pass to program (default NULL)
-k <ip>: RPC server ip address (default 127.0.0.1)
-n <port>: RPC server listen port (default 135)
-c <{clsid}>: CLSID (default BITS:{4991d34b-80a1-4291-83b6-3328366b9097})
-z only test CLSID and print token's user
```
