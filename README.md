malvm@ai-server /mnt/raid/projects/ElplatAI $ ping -4 -c 3 deb.debian.org
PING debian.map.fastlydns.net (199.232.174.132) 56(84) bytes of data.
64 bytes from 199.232.174.132: icmp_seq=1 ttl=60 time=37.6 ms
64 bytes from 199.232.174.132: icmp_seq=2 ttl=60 time=37.6 ms
64 bytes from 199.232.174.132: icmp_seq=3 ttl=60 time=37.6 ms

--- debian.map.fastlydns.net ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2003ms
rtt min/avg/max/mdev = 37.552/37.599/37.646/0.038 ms
malvm@ai-server /mnt/raid/projects/ElplatAI $ curl -v --connect-timeout 5 https://google.com curl -v --connect-timeout 5 https://8.8.8.8
* Host google.com:443 was resolved.
* IPv6: 2a00:1450:4010:c0f::8a, 2a00:1450:4010:c0f::66, 2a00:1450:4010:c0f::64, 2a00:1450:4010:c0f::71
* IPv4: 108.177.14.100, 108.177.14.113, 108.177.14.138, 108.177.14.101, 108.177.14.102, 108.177.14.139
*   Trying [2a00:1450:4010:c0f::8a]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::8a: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::66]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::66: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::64]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::64: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::71]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::71: Сеть недоступна
*   Trying 108.177.14.100:443...
* ALPN: curl offers h2,http/1.1
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
*   Trying [2a00:1450:4010:c0f::8a]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::8a: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::66]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::66: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::64]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::64: Сеть недоступна
*   Trying [2a00:1450:4010:c0f::71]:443...
* Immediate connect fail for 2a00:1450:4010:c0f::71: Сеть недоступна
*   Trying 108.177.14.100:443...
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384 / x25519 / id-ecPublicKey
* ALPN: server accepted h2
* Server certificate:
*  subject: CN=*.google.com
*  start date: May  7 15:51:36 2026 GMT
*  expire date: Jul 30 15:51:35 2026 GMT
*  subjectAltName: host "google.com" matched cert's "google.com"
*  issuer: C=US; O=Google Trust Services; CN=WE2
*  SSL certificate verify ok.
*   Certificate level 0: Public key type EC/prime256v1 (256/128 Bits/secBits), signed using ecdsa-with-SHA256
*   Certificate level 1: Public key type EC/prime256v1 (256/128 Bits/secBits), signed using ecdsa-with-SHA384
*   Certificate level 2: Public key type EC/secp384r1 (384/192 Bits/secBits), signed using ecdsa-with-SHA384
* Connected to google.com (108.177.14.100) port 443
* using HTTP/2
* [HTTP/2] [1] OPENED stream for https://google.com/
* [HTTP/2] [1] [:method: GET]
* [HTTP/2] [1] [:scheme: https]
* [HTTP/2] [1] [:authority: google.com]
* [HTTP/2] [1] [:path: /]
* [HTTP/2] [1] [user-agent: curl/8.15.0]
* [HTTP/2] [1] [accept: */*]
> GET / HTTP/2
> Host: google.com
> User-Agent: curl/8.15.0
> Accept: */*
>
* Request completely sent off
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
< HTTP/2 301
< location: https://www.google.com/
< content-type: text/html; charset=UTF-8
< content-security-policy-report-only: object-src 'none';base-uri 'self';script-src 'nonce-zf6PvtYHRtis9MVXTHU7DA' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp
< date: Wed, 20 May 2026 10:59:32 GMT
< expires: Fri, 19 Jun 2026 10:59:32 GMT
< cache-control: public, max-age=2592000
< server: gws
< content-length: 220
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.com/">here</A>.
</BODY></HTML>
* Connection #0 to host google.com left intact
* Could not resolve host: curl
* shutting down connection #1
curl: (6) Could not resolve host: curl
*   Trying 8.8.8.8:443...
* ALPN: curl offers h2,http/1.1
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384 / x25519 / RSASSA-PSS
* ALPN: server accepted h2
* Server certificate:
*  subject: CN=dns.google
*  start date: May  7 15:54:00 2026 GMT
*  expire date: Jul 30 15:53:59 2026 GMT
*  subjectAltName: host "8.8.8.8" matched cert's IP address!
*  issuer: C=US; O=Google Trust Services; CN=WR2
*  SSL certificate verify ok.
*   Certificate level 0: Public key type RSA (2048/112 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 1: Public key type RSA (2048/112 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 2: Public key type RSA (4096/152 Bits/secBits), signed using sha384WithRSAEncryption
* Connected to 8.8.8.8 (8.8.8.8) port 443
* using HTTP/2
* [HTTP/2] [1] OPENED stream for https://8.8.8.8/
* [HTTP/2] [1] [:method: GET]
* [HTTP/2] [1] [:scheme: https]
* [HTTP/2] [1] [:authority: 8.8.8.8]
* [HTTP/2] [1] [:path: /]
* [HTTP/2] [1] [user-agent: curl/8.15.0]
* [HTTP/2] [1] [accept: */*]
> GET / HTTP/2
> Host: 8.8.8.8
> User-Agent: curl/8.15.0
> Accept: */*
>
* Request completely sent off
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
< HTTP/2 302
< x-content-type-options: nosniff
< access-control-allow-origin: *
< location: https://dns.google/
< date: Wed, 20 May 2026 10:59:32 GMT
< content-type: text/html; charset=UTF-8
< server: HTTP server (unknown)
< content-length: 216
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>302 Moved</TITLE></HEAD><BODY>
<H1>302 Moved</H1>
The document has moved
<A HREF="https://dns.google/">here</A>.
</BODY></HTML>
* Connection #2 to host 8.8.8.8 left intact
malvm@ai-server /mnt/raid/projects/ElplatAI $ traceroute -4 199.232.174.132
-bash: traceroute: command not found
malvm@ai-server /mnt/raid/projects/ElplatAI $
