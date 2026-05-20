sudo iptables -L FORWARD -n -v --line-numbers
Скорее всего не хватает правила:
ACCEPT all -- docker0 * 0.0.0.0/0 0.0.0.0/0
Попробуй добавить временно и сразу проверить:
bash# Добавляем правило - разрешить исходящий трафик из контейнеров
sudo iptables -I DOCKER-INTERNAL 1 -i docker0 ! -o docker0 -j ACCEPT

# Проверяем сразу
docker run --rm python:3.13-slim-bookworm apt-get update
