## -X OPTIONS
```sh
└─$ curl -X OPTIONS -I http://10.129.95.234 -v                  
*   Trying 10.129.95.234:80...
* Connected to 10.129.95.234 (10.129.95.234) port 80
* using HTTP/1.x
> OPTIONS / HTTP/1.1
> Host: 10.129.95.234
> User-Agent: curl/8.14.1
> Accept: */*
> 
* Request completely sent off
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Date: Sun, 10 Aug 2025 12:02:26 GMT
Date: Sun, 10 Aug 2025 12:02:26 GMT
< Server: Microsoft-IIS/6.0
Server: Microsoft-IIS/6.0
< MicrosoftOfficeWebServer: 5.0_Pub
MicrosoftOfficeWebServer: 5.0_Pub
< X-Powered-By: ASP.NET
X-Powered-By: ASP.NET
< MS-Author-Via: MS-FP/4.0,DAV
MS-Author-Via: MS-FP/4.0,DAV
< Content-Length: 0
Content-Length: 0
< Accept-Ranges: none
Accept-Ranges: none
< DASL: <DAV:sql>
DASL: <DAV:sql>
< DAV: 1, 2
DAV: 1, 2
< Public: OPTIONS, TRACE, GET, HEAD, DELETE, PUT, POST, COPY, MOVE, MKCOL, PROPFIND, PROPPATCH, LOCK, UNLOCK, SEARCH
Public: OPTIONS, TRACE, GET, HEAD, DELETE, PUT, POST, COPY, MOVE, MKCOL, PROPFIND, PROPPATCH, LOCK, UNLOCK, SEARCH
< Allow: OPTIONS, TRACE, GET, HEAD, DELETE, COPY, MOVE, PROPFIND, PROPPATCH, SEARCH, MKCOL, LOCK, UNLOCK
Allow: OPTIONS, TRACE, GET, HEAD, DELETE, COPY, MOVE, PROPFIND, PROPPATCH, SEARCH, MKCOL, LOCK, UNLOCK
< Cache-Control: private
Cache-Control: private
< 

* Connection #0 to host 10.129.95.234 left intact
```
