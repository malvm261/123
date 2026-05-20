# Работает ли порт 80 с хоста?
curl -v --connect-timeout 5 http://deb.debian.org

# Работает ли порт 443 с хоста?
curl -v --connect-timeout 5 https://deb.debian.org
