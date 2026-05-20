# Проверь DNS
nslookup ghcr.io
cat /etc/resolv.conf

# Перезапусти resolved
sudo systemctl restart systemd-resolved

# Или пропиши DNS напрямую
sudo nano /etc/resolv.conf

nameserver 8.8.8.8
nameserver 8.8.4.4
