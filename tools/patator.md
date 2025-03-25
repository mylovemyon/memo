https://github.com/lanjelot/patator
## Usage
```
Patator 1.1.0 (https://github.com/lanjelot/patator) with Python-3.13.2
Usage: patator.py module --help

Available modules:
  + ftp_login     : Brute-force FTP
  + ssh_login     : Brute-force SSH
  + telnet_login  : Brute-force Telnet
  + smtp_login    : Brute-force SMTP
  + smtp_vrfy     : Enumerate valid users using SMTP VRFY
  + smtp_rcpt     : Enumerate valid users using SMTP RCPT TO
  + finger_lookup : Enumerate valid users using Finger
  + http_fuzz     : Brute-force HTTP
  + rdp_gateway   : Brute-force RDP Gateway
  + ajp_fuzz      : Brute-force AJP
  + pop_login     : Brute-force POP3
  + pop_passd     : Brute-force poppassd (http://netwinsite.com/poppassd/)
  + imap_login    : Brute-force IMAP4
  + ldap_login    : Brute-force LDAP
  + dcom_login    : Brute-force DCOM
  + smb_login     : Brute-force SMB
  + smb_lookupsid : Brute-force SMB SID-lookup
  + rlogin_login  : Brute-force rlogin
  + vmauthd_login : Brute-force VMware Authentication Daemon
  + mssql_login   : Brute-force MSSQL
  + oracle_login  : Brute-force Oracle
  + mysql_login   : Brute-force MySQL
  + mysql_query   : Brute-force MySQL queries
  + rdp_login     : Brute-force RDP (NLA)
  + pgsql_login   : Brute-force PostgreSQL
  + vnc_login     : Brute-force VNC
  + dns_forward   : Forward DNS lookup
  + dns_reverse   : Reverse DNS lookup
  + snmp_login    : Brute-force SNMP v1/2/3
  + ike_enum      : Enumerate IKE transforms
  + unzip_pass    : Brute-force the password of encrypted ZIP files
  + keystore_pass : Brute-force the password of Java keystore files
  + sqlcipher_pass : Brute-force the password of SQLCipher-encrypted databases
  + umbraco_crack : Crack Umbraco HMAC-SHA1 password hashes
  + tcp_fuzz      : Fuzz TCP services
  + dummy_test    : Testing module
```


## Global options
```
Global options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit

  Execution:
    -x arg              actions and conditions, see Syntax below
    --start=N           start from offset N in the product of all payload sets
    --stop=N            stop at offset N
    --resume=r1[,rN]*   resume previous run
    -e arg              encode everything between two tags, see Syntax below
    -C str              delimiter string in combo files (default is ':')
    -X str              delimiter string in conditions (default is ',')
    --allow-ignore-failures
                        failures cannot be ignored with -x (this is by design
                        to avoid false negatives) this option overrides this
                        safeguard
    -y                  automatically answer yes for all questions

  Optimization:
    --rate-limit=N      wait N seconds between each attempt (default is 0)
    --timeout=N         wait N seconds for a response before retrying payload
                        (default is 0)
    --max-retries=N     skip payload after N retries (default is 4) (-1 for
                        unlimited)
    -t N, --threads=N   number of threads (default is 10)
    --groups=GROUPS     default is to iterate over the cartesian product of
                        all payload sets, use this option to iterate over sets
                        simultaneously instead (aka pitchfork), see syntax
                        inside (default is '0,1..n')

  Logging:
    -l DIR              save output and response data into DIR
    -L SFX              automatically save into DIR/yyyy-mm-dd/hh:mm:ss_SFX
                        (DIR defaults to '/tmp/patator')
    -R FILE             save output to FILE
    --csv=FILE          save CSV results to FILE
    --xml=FILE          save XML results to FILE
    --hits=FILE         save found candidates to FILE

  Debugging:
    -d, --debug         enable debug messages
    --auto-progress=N   automatically display progress every N seconds

Syntax:
 -x actions:conditions

    actions    := action[,action]*
    action     := "ignore" | "retry" | "skip" | "free" | "quit" | "reset"
    conditions := condition=value[,condition=value]*
    condition  := "code" | "size" | "time" | "mesg" | "fgrep" | "egrep" | "clen"

    ignore      : do not report
    retry       : try payload again
    skip        : stop testing the same keyword value
    free        : stop testing the same option value
    quit        : terminate execution now
    reset       : close current connection in order to reconnect next time

    code        : match status code
    size        : match size (N or N-M or N- or -N)
    time        : match time (N or N-M or N- or -N)
    mesg        : match message
    fgrep       : search for string in mesg
    egrep       : search for regex in mesg
    clen        : match Content-Length header (N or N-M or N- or -N)

For example, to ignore all redirects to the home page:
... -x ignore:code=302,fgrep='Location: /home.html'

 -e tag:encoding

    tag        := any unique string (eg. T@G or _@@_ or ...)
    encoding   := "hex" | "unhex" | "b64" | "md5" | "sha1" | "url"

    hex         : encode in hexadecimal
    unhex       : decode from hexadecimal
    b64         : encode in base64
    md5         : hash in md5
    sha1        : hash in sha1
    url         : url encode

For example, to encode every password in base64:
... host=10.0.0.1 user=admin password=_@@_FILE0_@@_ -e _@@_:b64

Please read the README inside for more examples and usage information.
```


## http_fuzz
```
Usage: http_fuzz <module-options ...> [global-options ...]

Examples:
  http_fuzz url=http://10.0.0.1/FILE0 0=paths.txt -x ignore:code=404 -x ignore,retry:code=500
  http_fuzz url=http://10.0.0.1/manager/html user_pass=COMBO00:COMBO01 0=combos.txt -x ignore:code=401
  http_fuzz url=http://10.0.0.1/phpmyadmin/index.php method=POST body='pma_username=root&pma_password=FILE0&server=1&lang=en' 0=passwords.txt follow=1 accept_cookie=1 -x ignore:fgrep='Cannot log in to the MySQL server'

Module options:
  url           : target url (scheme://host[:port]/path?query)
  body          : body data
  header        : use custom headers
  method        : method to use [GET|POST|HEAD|...]
  raw_request   : load request from file
  scheme        : scheme [http|https]
  auto_urlencode: automatically perform URL-encoding [1|0]
  pathasis      : retain sequences of /../ or /./ [0|1]
  user_pass     : username and password for HTTP authentication (user:pass)
  auth_type     : type of HTTP authentication [basic | digest | ntlm]
  follow        : follow any Location redirect [0|1]
  max_follow    : redirection limit [5]
  accept_cookie : save received cookies to issue them in future requests [0|1]
  proxy         : proxy to use (host:port)
  proxy_type    : proxy type [http|socks4|socks4a|socks5]
  resolve       : hostname to IP address resolution to use (hostname:IP)
  ssl_cert      : client SSL certificate file (cert+key in PEM format)
  timeout_tcp   : seconds to wait for a TCP handshake [10]
  timeout       : seconds to wait for a HTTP response [20]
  before_urls   : comma-separated URLs to query before the main request
  before_header : use a custom header in the before_urls request
  before_egrep  : extract data from the before_urls response to place in the main request
  after_urls    : comma-separated URLs to query after the main request
  max_mem       : store no more than N bytes of request+response data in memory [-1 (unlimited)]
  persistent    : use persistent connections [1|0] 

ERROR: wrong usage. Please read the README inside for more information.
```
examples
basic認証のパスワードリスト攻撃
```sh
sudo docker run -it --rm -v $PWD/SecLists/Passwords:/mnt patator http_fuzz url=http://10.129.136.9:8080/manager/html user_pass=COMBO00:COMBO01 0=/mnt/Default-Credentials/tomcat-betterdefaultpasslist.txt -x ignore:code=401 -x ignore:code=403 auth_type=basic
```
