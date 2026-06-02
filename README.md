Нет, в стандартных образах marimo GPU не пробрасывается — это нужно настраивать вручную.

---

### Проброс NVIDIA GPU в Docker

**1. Установить NVIDIA Container Toolkit на хосте:**

```bash
curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | \
  sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg

curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | \
  sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
  sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list

sudo apt update
sudo apt install -y nvidia-container-toolkit
sudo nvidia-ctk runtime configure --runtime=docker
sudo systemctl restart docker
```

**2. Запустить marimo с GPU:**

```bash
docker run --gpus all -p 8080:8080 -it ghcr.io/marimo-team/marimo:latest-sql
```

Или конкретную карту:
```bash
docker run --gpus '"device=0"' -p 8080:8080 -it ghcr.io/marimo-team/marimo:latest-sql
```

**3. В Docker Compose:**

```yaml
services:
  marimo:
    image: ghcr.io/marimo-team/marimo:latest-sql
    ports:
      - "8080:8080"
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
```

---

### Проверить внутри контейнера

```bash
docker exec -it <container_name> nvidia-smi
```

---

### Важно

Стандартный образ `marimo:latest-sql` основан на `python:slim` — там нет CUDA. Если нужен **PyTorch / TensorFlow с GPU**, потребуется свой Dockerfile на базе CUDA-образа:

```dockerfile
FROM nvidia/cuda:12.1.0-cudnn8-runtime-ubuntu22.04

RUN pip install marimo torch torchvision

EXPOSE 8080
CMD ["marimo", "edit", "--host", "0.0.0.0", "--port", "8080"]
```

Если планируешь использовать GPU для ML — уточни, под что именно (PyTorch, TensorFlow, что-то другое), подберём нужный базовый образ.
