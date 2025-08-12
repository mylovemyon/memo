https://github.com/jetmore/swaks/blob/v20240103.0/doc/base.pod

## -t
```sh
└─$ swaks -t asterisk@beep.localdomain -s 10.129.156.206 
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO kali
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@kali>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: Tue, 12 Aug 2025 06:36:59 -0400
 -> To: asterisk@beep.localdomain
 -> From: kali@kali
 -> Subject: test Tue, 12 Aug 2025 06:36:59 -0400
 -> Message-Id: <20250812063659.334577@kali>
 -> X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/
 -> 
 -> This is a test mailing
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as C1797C0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```
```sh
From kali@kali.localdomain  Tue Aug 12 13:37:22 2025
Return-Path: <kali@kali.localdomain>
X-Original-To: asterisk@beep.localdomain
Delivered-To: asterisk@beep.localdomain
Received: from kali (unknown [10.10.16.23])
        by beep.localdomain (Postfix) with ESMTP id C1797C0003
        for <asterisk@beep.localdomain>; Tue, 12 Aug 2025 13:37:21 +0300 (EEST)
Date: Tue, 12 Aug 2025 06:36:59 -0400
To: asterisk@beep.localdomain
From: kali@kali
Subject: test Tue, 12 Aug 2025 06:36:59 -0400
Message-Id: <20250812063659.334577@kali>
X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/

This is a test mailing
```


## -f
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -s 10.129.156.206 
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO kali
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain> #変化
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: Tue, 12 Aug 2025 06:35:27 -0400
 -> To: asterisk@beep.localdomain
 -> From: kali@beep.localdomain #変化
 -> Subject: test Tue, 12 Aug 2025 06:35:27 -0400
 -> Message-Id: <20250812063527.333790@kali>
 -> X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/
 -> 
 -> This is a test mailing
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as 0CA4DC0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```
```sh
From kali@beep.localdomain  Tue Aug 12 13:35:50 2025 #変化
Return-Path: <kali@beep.localdomain>
X-Original-To: asterisk@beep.localdomain
Delivered-To: asterisk@beep.localdomain
Received: from kali (unknown [10.10.16.23])
        by beep.localdomain (Postfix) with ESMTP id 0CA4DC0003
        for <asterisk@beep.localdomain>; Tue, 12 Aug 2025 13:35:49 +0300 (EEST)
Date: Tue, 12 Aug 2025 06:35:27 -0400
To: asterisk@beep.localdomain
From: kali@beep.localdomain #変化
Subject: test Tue, 12 Aug 2025 06:35:27 -0400
Message-Id: <20250812063527.333790@kali>
X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/

This is a test mailing
```


## -h
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -h 'Hi' -s 10.129.156.206
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO Hi #変化
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: Tue, 12 Aug 2025 06:47:43 -0400
 -> To: asterisk@beep.localdomain
 -> From: kali@beep.localdomain
 -> Subject: test Tue, 12 Aug 2025 06:47:43 -0400
 -> Message-Id: <20250812064743.339915@kali>
 -> X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/
 -> 
 -> This is a test mailing
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as 6B4D7C0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```


## --protocol
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -h 'Hi' --protocol esmtp -s 10.129.156.206
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO Hi #指定したプロトコルによって変化
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: Tue, 12 Aug 2025 06:49:22 -0400
 -> To: asterisk@beep.localdomain
 -> From: kali@beep.localdomain
 -> Subject: test Tue, 12 Aug 2025 06:49:22 -0400
 -> Message-Id: <20250812064922.340755@kali>
 -> X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/
 -> 
 -> This is a test mailing
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as 196C9C0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```


## --body
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -h 'Hi' --protocol esmtp --body '0' -s 10.129.156.206 
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO Hi
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: Tue, 12 Aug 2025 06:59:26 -0400
 -> To: asterisk@beep.localdomain
 -> From: kali@beep.localdomain
 -> Subject: test Tue, 12 Aug 2025 06:59:26 -0400
 -> Message-Id: <20250812065926.345909@kali>
 -> X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/
 -> 
 -> 0 #変化
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as 593C1C0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```
```sh
From kali@beep.localdomain  Tue Aug 12 13:59:48 2025
Return-Path: <kali@beep.localdomain>
X-Original-To: asterisk@beep.localdomain
Delivered-To: asterisk@beep.localdomain
Received: from Hi (unknown [10.10.16.23])
        by beep.localdomain (Postfix) with ESMTP id 593C1C0003
        for <asterisk@beep.localdomain>; Tue, 12 Aug 2025 13:59:48 +0300 (EEST)
Date: Tue, 12 Aug 2025 06:59:26 -0400
To: asterisk@beep.localdomain
From: kali@beep.localdomain
Subject: test Tue, 12 Aug 2025 06:59:26 -0400
Message-Id: <20250812065926.345909@kali>
X-Mailer: swaks v20240103.0 jetmore.org/john/code/swaks/

0 #変化
```


## --h
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -h 'Hi' --protocol esmtp --h-Date '0' --h-To '0' --h-From '0' --h-Subject '0' --h-Message-Id '0' --h-X-Mailer '0' --body '0' -s 10.129.156.206
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO Hi
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> Date: 0 #変化
 -> To: 0 #変化
 -> From: 0 #変化
 -> Subject: 0 #変化
 -> Message-Id: 0 #変化
 -> X-Mailer: 0 #変化
 -> 
 -> 0
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as 03EAEC0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```
```sh
From kali@beep.localdomain  Tue Aug 12 13:58:16 2025
Return-Path: <kali@beep.localdomain>
X-Original-To: asterisk@beep.localdomain
Delivered-To: asterisk@beep.localdomain
Received: from Hi (unknown [10.10.16.23])
        by beep.localdomain (Postfix) with ESMTP id 03EAEC0003
        for <asterisk@beep.localdomain>; Tue, 12 Aug 2025 13:58:15 +0300 (EEST)
Date: 0 #変化
To: 0 #変化
From: 0 #変化
Subject: 0 #変化
Message-Id: 0 #変化
X-Mailer: 0 #変化

0
```


## -d
```sh
└─$ swaks -f kali@beep.localdomain -t asterisk@beep.localdomain -h 'Hi' --protocol esmtp -d "a" -s 10.129.156.206
=== Trying 10.129.156.206:25...
=== Connected to 10.129.156.206.
<-  220 beep.localdomain ESMTP Postfix
 -> EHLO Hi
<-  250-beep.localdomain
<-  250-PIPELINING
<-  250-SIZE 10240000
<-  250-VRFY
<-  250-ETRN
<-  250-ENHANCEDSTATUSCODES
<-  250-8BITMIME
<-  250 DSN
 -> MAIL FROM:<kali@beep.localdomain>
<-  250 2.1.0 Ok
 -> RCPT TO:<asterisk@beep.localdomain>
<-  250 2.1.5 Ok
 -> DATA
<-  354 End data with <CR><LF>.<CR><LF>
 -> a #変化
 -> 
 -> 
 -> .
<-  250 2.0.0 Ok: queued as ACCADC0003
 -> QUIT
<-  221 2.0.0 Bye
=== Connection closed with remote host.
```
```sh
From kali@beep.localdomain  Tue Aug 12 14:05:31 2025
Return-Path: <kali@beep.localdomain>
X-Original-To: asterisk@beep.localdomain
Delivered-To: asterisk@beep.localdomain
Received: from Hi (unknown [10.10.16.23])
        by beep.localdomain (Postfix) with ESMTP id ACCADC0003
        for <asterisk@beep.localdomain>; Tue, 12 Aug 2025 14:05:30 +0300 (EEST)
Message-Id: <20250812110530.ACCADC0003@beep.localdomain>
Date: Tue, 12 Aug 2025 14:05:30 +0300 (EEST)
From: kali@beep.localdomain
To: undisclosed-recipients:;

a #変化
```
