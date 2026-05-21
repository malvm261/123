malvm@malvm-Atlas-H256:~$ squid -k reconfigure
2026/05/21 17:09:05| Processing Configuration File: /etc/squid/squid.conf (depth 0)
2026/05/21 17:09:05| WARNING: HTTP requires the use of Via
2026/05/21 17:09:05| ERROR: unable to load certificate file '/etc/squid/ssl_cert/myCA.pem': error:8000000D:system library::Permission denied
2026/05/21 17:09:05| WARNING: 'HTTP_port [::]:3128' missing certificate in '/etc/squid/ssl_cert/myCA.pem'
2026/05/21 17:09:05| Not currently OK to rewrite swap log.
2026/05/21 17:09:05| storeDirWriteCleanLogs: Operation aborted.
2026/05/21 17:09:05| FATAL: No valid signing certificate configured for HTTP_port [::]:3128
2026/05/21 17:09:05| Squid Cache (Version 6.14): Terminated abnormally.
CPU Usage: 0.015 seconds = 0.014 user + 0.001 sys
Maximum Resident Size: 72464 KB
Page faults with physical i/o: 0
malvm@malvm-Atlas-H256:~$
