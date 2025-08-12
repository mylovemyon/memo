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
