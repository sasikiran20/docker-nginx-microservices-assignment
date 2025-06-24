FROM ghcr.io/astral-sh/uv:python3.13-bookworm-slim

WORKDIR /app

COPY . .

RUN uv sync --locked

EXPOSE 8002

CMD ["uv", "run", "app.py"]
