FROM arm64v8/python:3.12-slim
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

WORKDIR /app/harmonize

RUN apt-get update && apt-get install -y \
    avahi-daemon \
    libgl1 \
    libglib2.0-0 \
    git

RUN git clone https://github.com/takitsu21/HarmonizeProject.git /app/harmonize

RUN uv sync --frozen

CMD [ "uv", "run", "harmonize.py", "-a", "8"]
