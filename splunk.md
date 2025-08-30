```
index="botsv*" sourcetype=WinEventLog EventCode=4624
| eval dest_host = upper(dvc_nt_host)
| stats count by src_nt_host,dest_host
| eval from=src_nt_host,to=dest_host,type="desktop"
```
``` 
index="botsv*" EventCode=4624 Logon_Type=3 ComputerName IN ("*klagerf*", "*btun*" , "*FYODOR-L*" , "*venus*")
| rename ComputerName as dest_host
| rename src_nt_host as src_host
| stats count by src_host,dest_host
| eval from=src_host, to=dest_host
| fields from, to, count
```
