# Смотрим все правила NAT - ищем редирект порта 80
sudo iptables -t nat -L -n -v

# Смотрим FILTER цепочки - ищем DROP для порта 80
sudo iptables -L -n -v | grep -E "80|DROP|REJECT"

# И отдельно FORWARD цепочку
sudo iptables -L FORWARD -n -v
