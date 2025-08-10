```sh
└─$ davtest -url http://10.129.95.234 -cleanup -debug 3
********************************************************
 Testing DAV connection
new_resource: For http://10.129.95.234/, creating new resource
OPEN            SUCCEED:                http://10.129.95.234
********************************************************
NOTE    Random string for this session: FBz20A
********************************************************
 Creating directory
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/, creating new resource
MKCOL           SUCCEED:                Created http://10.129.95.234/DavTestDir_FBz20A
new_resource: For http://10.129.95.234, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/, creating new resource
********************************************************
 Sending test files
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.aspx, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.aspx, creating new resource
PUT     aspx    FAIL
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm, creating new resource
PUT     cfm     SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp, creating new resource
PUT     jsp     SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php, creating new resource
PUT     php     SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.shtml, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.shtml, creating new resource
PUT     shtml   FAIL
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml, creating new resource
PUT     jhtml   SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.asp, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.asp, creating new resource
PUT     asp     FAIL
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cgi, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cgi, creating new resource
PUT     cgi     FAIL
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html, creating new resource
PUT     html    SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl, creating new resource
PUT     pl      SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt, creating new resource
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt, creating new resource
PUT     txt     SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt
********************************************************
 Checking for test file execution
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm, creating new resource
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm;.txt, creating new resource
EXEC    cfm     FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp, creating new resource
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp;.txt, creating new resource
EXEC    jsp     FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php, creating new resource
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php;.txt, creating new resource
EXEC    php     FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml, creating new resource
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml;.txt, creating new resource
EXEC    jhtml   FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html, creating new resource
EXEC    html    SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html;.txt, creating new resource
EXEC    html    FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl, creating new resource
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl;.txt, creating new resource
EXEC    pl      FAIL
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt, creating new resource
EXEC    txt     SUCCEED:        http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt
get: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt;.txt -> SCALAR(0x55e819c33358)
new_resource: For http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt;.txt, creating new resource
EXEC    txt     FAIL
********************************************************
 Cleaning up
new_resource: For http://10.129.95.234/DavTestDir_FBz20A, creating new resource
DELETE          FAIL:   http://10.129.95.234/DavTestDir_FBz20A
new_resource: For http://10.129.95.234/DavTestDir_FBz20A, creating new resource

********************************************************
/usr/bin/davtest Summary:
Created: http://10.129.95.234/DavTestDir_FBz20A
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.cfm
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jsp
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.php
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.jhtml
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.pl
PUT File: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt
Executes: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.html
Executes: http://10.129.95.234/DavTestDir_FBz20A/davtest_FBz20A.txt
```
