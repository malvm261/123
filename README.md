# Пингуется ли вообще?
ping -4 -c 3 deb.debian.org

# А другие сайты?
curl -v --connect-timeout 5 https://google.com
curl -v --connect-timeout 5 https://8.8.8.8

# Маршрут до адреса
traceroute -4 199.232.174.132
