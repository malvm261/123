# ---- сборка зависимостей ----
FROM python:3.13-slim-bookworm AS builder

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential gcc g++ \
    && rm -rf /var/lib/apt/lists/*

COPY --from=ghcr.io/astral-sh/uv:0.5.31 /uv /usr/local/bin/

WORKDIR /project
ENV UV_LINK_MODE=copy

# Слой кэша зависимостей (меняется только при изменении lock-файла)
COPY pyproject.toml uv.lock README.md ./
RUN uv sync --frozen --no-dev --no-install-project

# Установка самого пакета
COPY src ./src
RUN uv sync --frozen --no-dev


# ---- финальный образ ----
FROM python:3.13-slim-bookworm

RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates \
    libgl1 \
    libglib2.0-0 \
    libgomp1 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /project
ENV PATH="/project/.venv/bin:${PATH}"

COPY --from=builder /project /project

CMD ["python", "-m", "elplatai.main"]
