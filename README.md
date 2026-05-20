FROM python:3.13-alpine

RUN apk add --no-cache \
    gcc g++ musl-dev \
    libgl \
    glib \
    libgomp

COPY --from=ghcr.io/astral-sh/uv:0.5.31 /uv /usr/local/bin/

WORKDIR /project
ENV UV_LINK_MODE=copy

COPY pyproject.toml uv.lock README.md ./
RUN uv sync --frozen --no-dev --no-install-project

COPY src ./src
RUN uv sync --frozen --no-dev

ENV PATH="/project/.venv/bin:${PATH}"

CMD ["python", "-m", "elplatai.main"]
