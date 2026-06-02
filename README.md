Добавь `Dockerfile` рядом с `compose.yaml`:

```dockerfile
FROM ghcr.io/marimo-team/marimo:latest-sql

USER root
RUN apt-get update && apt-get install -y \
    libxcb1 \
    libgl1 \
    libglib2.0-0 \
    && rm -rf /var/lib/apt/lists/*

USER app_user
```

И измени `compose.yaml` — замени `image` на `build`:

```yaml
services:
  marimo:
    build: .
    ports:
      - "3000:8080"
    environment:
      - QT_QPA_PLATFORM=offscreen
    volumes:
      - ./notebooks:/app
```

Затем пересобери и запусти:
```bash
docker compose down
docker compose up -d --build
```
