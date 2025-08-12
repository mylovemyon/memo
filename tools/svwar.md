sipはよくわかんね  
https://www.infraexpert.com/study/telephony4.html


## -e
extensionを指定
```sh
└─$ svwar -e 1 10.129.229.183        
ERROR:TakeASip:SIP server replied with an authentication request for an unknown extension. Set --force to force a scan.
WARNING:root:found nothing

└─$ svwar -e 1 10.129.229.183 -vv
DEBUG:root:started logging
DEBUG:TakeASip:external ip was not set
INFO:TakeASip:trying to get self ip .. might take a while
INFO:root:scan started at 2025-08-11 21:22:00.580644
INFO:root:start your engines
DEBUG:TakeASip:binding to any:5060
ERROR:TakeASip:SIP server replied with an authentication request for an unknown extension. Set --force to force a scan.
WARNING:root:found nothing
INFO:root:Total time: 0:00:00.510649
                                                                                                                    
└─$ svwar -e 1 10.129.229.183 --debug 
('10.129.229.183', 5060)
b'SIP/2.0 100 Trying\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1355802389;received=10.10.16.23;rport=5060\r\nFrom: "728303743"<sip:728303743@10.129.229.183>;tag=37323833303337343301383430323035383637\r\nTo: "728303743"<sip:728303743@10.129.229.183>\r\nCall-ID: 4037479435\r\nCSeq: 1 REGISTER\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 401 Unauthorized\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1355802389;received=10.10.16.23;rport=5060\r\nFrom: "728303743"<sip:728303743@10.129.229.183>;tag=37323833303337343301383430323035383637\r\nTo: "728303743"<sip:728303743@10.129.229.183>;tag=as553f2cf5\r\nCall-ID: 4037479435\r\nCSeq: 1 REGISTER\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nWWW-Authenticate: Digest algorithm=MD5, realm="asterisk", nonce="040d577d"\r\nContent-Length: 0\r\n\r\n'
ERROR:TakeASip:SIP server replied with an authentication request for an unknown extension. Set --force to force a scan.
WARNING:root:found nothing
```


## -m INVITE
デフォルトでは、REGISTERオプションが使用される
### 実在しないextensionの場合
```sh
└─$ svwar -e 1 -m INVITE 10.129.229.183        
WARNING:TakeASip:using an INVITE scan on an endpoint (i.e. SIP phone) may cause it to ring and wake up people in the middle of the night
WARNING:root:found nothing

└─$ svwar -e 1 -m INVITE 10.129.229.183 --debug 
WARNING:TakeASip:using an INVITE scan on an endpoint (i.e. SIP phone) may cause it to ring and wake up people in the middle of the night
('10.129.229.183', 5060)
b'SIP/2.0 100 Trying\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2077602556;received=10.10.16.23;rport=5060\r\nFrom: "3273563901"<sip:3273563901@10.129.229.183>;tag=333237333536333930310133313932383837333938\r\nTo: "3273563901"<sip:3273563901@10.129.229.183>\r\nCall-ID: 493845160\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:3273563901@10.129.229.183:5060>\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2077602556;received=10.10.16.23;rport=5060\r\nFrom: "3273563901"<sip:3273563901@10.129.229.183>;tag=333237333536333930310133313932383837333938\r\nTo: "3273563901"<sip:3273563901@10.129.229.183>;tag=as66da225c\r\nCall-ID: 493845160\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:3273563901@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 231\r\n\r\nv=0\r\no=root 1973605095 1973605095 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 16370 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2077602556;received=10.10.16.23;rport=5060\r\nFrom: "3273563901"<sip:3273563901@10.129.229.183>;tag=333237333536333930310133313932383837333938\r\nTo: "3273563901"<sip:3273563901@10.129.229.183>;tag=as66da225c\r\nCall-ID: 493845160\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:3273563901@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 231\r\n\r\nv=0\r\no=root 1973605095 1973605095 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 16370 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 100 Trying\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1301501541;received=10.10.16.23;rport=5060\r\nFrom: "1"<sip:1@10.129.229.183>;tag=310133353630393438343533\r\nTo: "1"<sip:1@10.129.229.183>\r\nCall-ID: 1898085678\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:1@10.129.229.183:5060>\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1301501541;received=10.10.16.23;rport=5060\r\nFrom: "1"<sip:1@10.129.229.183>;tag=310133353630393438343533\r\nTo: "1"<sip:1@10.129.229.183>;tag=as1fb7461b\r\nCall-ID: 1898085678\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:1@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 231\r\n\r\nv=0\r\no=root 1661516714 1661516714 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 10282 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-3140363303;received=10.10.16.23;rport=5060\r\nFrom: "3273563901"<sip:3273563901@10.129.229.183>;tag=333237333536333930310133313932383837333938;tag=4e6f6e650131383936303137383138\r\nTo: "3273563901"<sip:3273563901@10.129.229.183>;tag=as66da225c\r\nCall-ID: 493845160\r\nCSeq: 2 BYE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1301501541;received=10.10.16.23;rport=5060\r\nFrom: "1"<sip:1@10.129.229.183>;tag=310133353630393438343533\r\nTo: "1"<sip:1@10.129.229.183>;tag=as1fb7461b\r\nCall-ID: 1898085678\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:1@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 231\r\n\r\nv=0\r\no=root 1661516714 1661516714 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 10282 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1247549456;received=10.10.16.23;rport=5060\r\nFrom: "1"<sip:1@10.129.229.183>;tag=310133353630393438343533;tag=4e6f6e650132363134343139313733\r\nTo: "1"<sip:1@10.129.229.183>;tag=as1fb7461b\r\nCall-ID: 1898085678\r\nCSeq: 2 BYE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-950449024;received=10.10.16.23;rport=5060\r\nFrom: "1"<sip:1@10.129.229.183>;tag=310133353630393438343533;tag=4e6f6e650134313238363136343736\r\nTo: "1"<sip:1@10.129.229.183>;tag=as1fb7461b\r\nCall-ID: 1898085678\r\nCSeq: 2 BYE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
WARNING:root:found nothing
```
### 実在するextensionの場合
```sh
└─$ svwar -e 233 -m INVITE 10.129.229.183        
WARNING:TakeASip:using an INVITE scan on an endpoint (i.e. SIP phone) may cause it to ring and wake up people in the middle of the night
+-----------+----------------+
| Extension | Authentication |
+===========+================+
| 233       | reqauth        |
+-----------+----------------+

└─$ svwar -e 233 -m INVITE 10.129.229.183 --debug
WARNING:TakeASip:using an INVITE scan on an endpoint (i.e. SIP phone) may cause it to ring and wake up people in the middle of the night
('10.129.229.183', 5060)
b'SIP/2.0 100 Trying\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2934966288;received=10.10.16.23;rport=5060\r\nFrom: "2770421823"<sip:2770421823@10.129.229.183>;tag=3237373034323138323301343130323630393537\r\nTo: "2770421823"<sip:2770421823@10.129.229.183>\r\nCall-ID: 3043150590\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:2770421823@10.129.229.183:5060>\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2934966288;received=10.10.16.23;rport=5060\r\nFrom: "2770421823"<sip:2770421823@10.129.229.183>;tag=3237373034323138323301343130323630393537\r\nTo: "2770421823"<sip:2770421823@10.129.229.183>;tag=as2a522ac8\r\nCall-ID: 3043150590\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:2770421823@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 227\r\n\r\nv=0\r\no=root 81885616 81885616 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 16904 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-2934966288;received=10.10.16.23;rport=5060\r\nFrom: "2770421823"<sip:2770421823@10.129.229.183>;tag=3237373034323138323301343130323630393537\r\nTo: "2770421823"<sip:2770421823@10.129.229.183>;tag=as2a522ac8\r\nCall-ID: 3043150590\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContact: <sip:2770421823@10.129.229.183:5060>\r\nContent-Type: application/sdp\r\nContent-Length: 227\r\n\r\nv=0\r\no=root 81885616 81885616 IN IP4 10.129.229.183\r\ns=Asterisk PBX 1.8.7.0\r\nc=IN IP4 10.129.229.183\r\nt=0 0\r\nm=audio 16904 RTP/AVP 0 8 3\r\na=rtpmap:0 PCMU/8000\r\na=rtpmap:8 PCMA/8000\r\na=rtpmap:3 GSM/8000\r\na=ptime:20\r\na=sendrecv\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 401 Unauthorized\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1910455167;received=10.10.16.23;rport=5060\r\nFrom: "233"<sip:233@10.129.229.183>;tag=3233330131393730393837333339\r\nTo: "233"<sip:233@10.129.229.183>;tag=as6feb64fe\r\nCall-ID: 2165139524\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nWWW-Authenticate: Digest algorithm=MD5, realm="asterisk", nonce="6b71b35c"\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 200 OK\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1524475094;received=10.10.16.23;rport=5060\r\nFrom: "2770421823"<sip:2770421823@10.129.229.183>;tag=3237373034323138323301343130323630393537;tag=4e6f6e650132373031393632363937\r\nTo: "2770421823"<sip:2770421823@10.129.229.183>;tag=as2a522ac8\r\nCall-ID: 3043150590\r\nCSeq: 2 BYE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 401 Unauthorized\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-1910455167;received=10.10.16.23;rport=5060\r\nFrom: "233"<sip:233@10.129.229.183>;tag=3233330131393730393837333339\r\nTo: "233"<sip:233@10.129.229.183>;tag=as6feb64fe\r\nCall-ID: 2165139524\r\nCSeq: 1 INVITE\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nWWW-Authenticate: Digest algorithm=MD5, realm="asterisk", nonce="6b71b35c"\r\nContent-Length: 0\r\n\r\n'
+-----------+----------------+
| Extension | Authentication |
+===========+================+
| 233       | reqauth        |
+-----------+----------------+
```


## -t
```sh
└─$ svwar -t 0.1 -e 0-300 -m INVITE 10.129.229.183
WARNING:TakeASip:using an INVITE scan on an endpoint (i.e. SIP phone) may cause it to ring and wake up people in the middle of the night
+-----------+----------------+
| Extension | Authentication |
+===========+================+
| 233       | reqauth        |
+-----------+----------------+
```


## -D
```sh
└─$ svwar -D 10.129.229.183 --debug
('10.129.229.183', 5060)
b'SIP/2.0 100 Trying\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-3919157430;received=10.10.16.23;rport=5060\r\nFrom: "3284015058"<sip:3284015058@10.129.229.183>;tag=333238343031353035380132303635343238393237\r\nTo: "3284015058"<sip:3284015058@10.129.229.183>\r\nCall-ID: 2762273390\r\nCSeq: 1 REGISTER\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nContent-Length: 0\r\n\r\n'
('10.129.229.183', 5060)
b'SIP/2.0 401 Unauthorized\r\nVia: SIP/2.0/UDP 127.0.1.1:5060;branch=z9hG4bK-3919157430;received=10.10.16.23;rport=5060\r\nFrom: "3284015058"<sip:3284015058@10.129.229.183>;tag=333238343031353035380132303635343238393237\r\nTo: "3284015058"<sip:3284015058@10.129.229.183>;tag=as70cd162f\r\nCall-ID: 2762273390\r\nCSeq: 1 REGISTER\r\nServer: FPBX-2.8.1(1.8.7.0)\r\nAllow: INVITE, ACK, CANCEL, OPTIONS, BYE, REFER, SUBSCRIBE, NOTIFY, INFO, PUBLISH\r\nSupported: replaces, timer\r\nWWW-Authenticate: Digest algorithm=MD5, realm="asterisk", nonce="40fd3632"\r\nContent-Length: 0\r\n\r\n'
ERROR:TakeASip:SIP server replied with an authentication request for an unknown extension. Set --force to force a scan.
WARNING:root:found nothing
```
