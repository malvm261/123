# Проверь DNS
nslookup ghcr.io
cat /etc/resolv.conf

# Перезапусти resolved
sudo systemctl restart systemd-resolved

# Или пропиши DNS напрямую
sudo nano /etc/resolv.conf

nameserver 8.8.8.8
nameserver 8.8.4.4


-----------------------------------------------------
(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ nslookup ghcr.io
Server:         127.0.0.53
Address:        127.0.0.53#53

Non-authoritative answer:
Name:   ghcr.io
Address: 140.82.121.33

(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ cat /etc/resolv.conf
# This is /run/systemd/resolve/stub-resolv.conf managed by man:systemd-resolved(8).
# Do not edit.
#
# This file might be symlinked as /etc/resolv.conf. If you're looking at
# /etc/resolv.conf and seeing this text, you have followed the symlink.
#
# This is a dynamic resolv.conf file for connecting local clients to the
# internal DNS stub resolver of systemd-resolved. This file lists all
# configured search domains.
#
# Run "resolvectl status" to see details about the uplink DNS servers
# currently in use.
#
# Third party programs should typically not access this file directly, but only
# through the symlink at /etc/resolv.conf. To manage man:resolv.conf(5) in a
# different way, replace this symlink by a static file or a different symlink.
#
# See man:systemd-resolved.service(8) for details about the supported modes of
# operation for /etc/resolv.conf.

nameserver 127.0.0.53
options edns0 trust-ad
search .
(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ 
