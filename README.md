# ---- сборка зависимостей ----
FROM python:3.13.12-slim-bookworm@sha256:a58daefb915e1e03ad48f3ca4df8832065412c5c35cacb9d39f4229184de12b6 AS builder
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential gcc g++ \
    && rm -rf /var/lib/apt/lists/*
COPY --from=ghcr.io/astral-sh/uv:0.5.31 /uv /usr/local/bin/
WORKDIR /project
ENV UV_LINK_MODE=copy
COPY pyproject.toml uv.lock README.md ./
RUN uv sync --frozen --no-dev --no-install-project
COPY src ./src
RUN uv sync --frozen --no-dev

# ---- финальный образ ----
FROM python:3.13.12-slim-bookworm@sha256:a58daefb915e1e03ad48f3ca4df8832065412c5c35cacb9d39f4229184de12b6
RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates libgl1 libglib2.0-0 libgomp1 \
    && rm -rf /var/lib/apt/lists/*
WORKDIR /project
ENV PATH="/project/.venv/bin:${PATH}"

# venv отдельным слоем — кэшируется, меняется только при изменении зависимостей
COPY --from=builder /project/.venv /project/.venv

# src отдельным слоем — лёгкий, меняется часто
COPY --from=builder /project/src /project/src

CMD ["python", "-m", "elplatai.main"]
