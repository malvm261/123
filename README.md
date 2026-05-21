malvm@squid ~ $ cat /etc/squid/squid.conf
# ==========================================
# === СЕТИ =================================
# ==========================================
acl admnet src 172.21.165.0/24
acl media_allow src 172.21.165.0/24 172.21.166.0/24 172.21.167.0/24 172.21.169.0/24 172.21.170.0/24 172.21.171.0/24 172.21.172.0/24
acl media_deny src 172.21.168.0/24
# Разрешённые порты
# 8080 ammyy admin
# 8081 portal.fedsfm.ru
# 44444, 44335, 44334, 44333, 53 ассистент
acl SSL_ports port 443 80 8080 8081 44444 44335 44334 44333 53
acl Safe_ports port 21 80 443 1025-65535
acl CONNECT method CONNECT

# ==========================================
# === SSL BUMP =============================
# ==========================================

# Адреса и сайты, где нельзя bump
acl nobump_ip dst 91.223.44.0/24
acl ammyy_ip dst "/etc/squid/include/ammyy_admin.txt"
acl assistant_ip dst "/etc/squid/include/assistant_ip.txt"
acl nobump_sites ssl::server_name "/etc/squid/include/nobump_sites.txt"

# Центр сертификации
sslcrtd_program /usr/libexec/squid/security_file_certgen -s /var/spool/squid/ssl_db -M 4MB
sslcrtd_children 5

# Этап SslBump
acl step1 at_step SslBump1

# Логика SSL Bump
ssl_bump splice assistant_ip
ssl_bump splice ammyy_ip
ssl_bump splice nobump_sites
ssl_bump splice nobump_ip
ssl_bump peek step1
ssl_bump bump media_allow
ssl_bump bump media_deny
ssl_bump splice all

# ==========================================
# === МЕДИА ФИЛЬТРАЦИЯ =====================
# ==========================================

acl media_content rep_mime_type -i ^video/
acl media_content rep_mime_type -i ^audio/
acl media_content rep_mime_type -i application/ogg
acl media_content rep_mime_type -i application/x-mpegurl
acl media_content rep_mime_type -i application/vnd.apple.mpegurl
acl media_content rep_mime_type -i application/dash+xml

acl media_urls urlpath_regex -i \.(mp4|avi|mkv|mov|wmv|flv|webm|mp3|wav|flac|aac|ogg|m4a|wma|m3u8|ts)$
acl media_urls urlpath_regex -i /video/|/audio/|/stream/|/media/

reply_body_max_size 50 KB media_content media_deny
reply_body_max_size 50 KB media_urls media_deny

# ==========================================
# === ПОРТЫ ================================
# ==========================================
http_port 3128 ssl-bump \
    cert=/etc/squid/ssl_cert/myCA_combined.pem \
    generate-host-certificates=on \
    dynamic_cert_mem_cache_size=4MB

http_port 3130

visible_hostname squid.el-plat.ru

# ==========================================
# === ПРАВИЛА ДОСТУПА ======================
# ==========================================

# Доступ Ammyy
http_access allow ammyy_ip
http_access allow assistant_ip

# Получение промежуточных сертификатов
acl intermediate_fetching transaction_initiator certificate-fetching
http_access allow intermediate_fetching

# Общая безопасность
http_access deny !Safe_ports
http_access deny CONNECT !SSL_ports

# Доступ к интерфейсу Squid
http_access allow admnet manager
http_access deny manager

# Основной доступ
http_access allow localhost
http_access allow media_allow
http_access allow media_deny

# Все остальные запреты
http_access deny all

# ==========================================
# === КЕШ ==================================
# ==========================================

cache_mem 3 GB
maximum_object_size_in_memory 5 MB
memory_replacement_policy lru

cache_dir ufs /var/spool/squid 5000 16 256
maximum_object_size 10 MB
cache_swap_low 90
cache_swap_high 95
coredump_dir /var/spool/squid

refresh_pattern -i \.(jpg|jpeg|png|gif|ico|bmp|tiff|svg)$     1440 90% 10080
refresh_pattern -i \.(css|js|woff|woff2|ttf|eot)$             1440 90% 10080
refresh_pattern -i \.(zip|gz|tgz|bz2|rar|7z|tar)$             10080 90% 43200
refresh_pattern -i \.(pdf|doc|docx|xls|xlsx|ppt|pptx|txt)$    1440 90% 10080
refresh_pattern -i (/cgi-bin/|\?) 0 0% 0
refresh_pattern . 30 20% 4320

pid_filename /run/squid.pid
malvm@squid ~ $


malvm@squid ~ $ cat /etc/squid/include/nobump_sites.txt
.tradingview.com
.tradingview.io
.tvcdn.co
.alice.yandex.ru
lkulgost.nalog.ru
.fedsfm.ru
.gov.ru
портал-тп.рф
.kontur-f.ru
malvm@squid ~ $
