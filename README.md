malvm@ai-server /mnt/raid/projects/ElplatAI $ curl -v --connect-timeout 5 http://deb.debian.org
* Host deb.debian.org:80 was resolved.
* IPv6: 2a04:4e42:6b::644
* IPv4: 199.232.174.132
*   Trying [2a04:4e42:6b::644]:80...
* Immediate connect fail for 2a04:4e42:6b::644: Сеть недоступна
*   Trying 199.232.174.132:80...
* Connection timed out after 5002 milliseconds
* closing connection #0
curl: (28) Connection timed out after 5002 milliseconds
malvm@ai-server /mnt/raid/projects/ElplatAI $ curl -v --connect-timeout 5 https://deb.debian.org
* Host deb.debian.org:443 was resolved.
* IPv6: 2a04:4e42:6b::644
* IPv4: 199.232.174.132
*   Trying [2a04:4e42:6b::644]:443...
* Immediate connect fail for 2a04:4e42:6b::644: Сеть недоступна
*   Trying 199.232.174.132:443...
* Connection timed out after 5002 milliseconds
* closing connection #0
curl: (28) Connection timed out after 5002 milliseconds
malvm@ai-server /mnt/raid/projects/ElplatAI $
