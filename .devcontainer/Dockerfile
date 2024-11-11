FROM mcr.microsoft.com/devcontainers/universal:2-linux

WORKDIR /opt/app

COPY requirements.txt /opt/app

RUN apt-get update && \
    pip install --no-cache-dir --upgrade pip && \
    pip install -r requirements.txt

CMD ["cat", "/etc/os-release"]
