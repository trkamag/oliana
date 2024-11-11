FROM mcr.microsoft.com/devcontainers/universal:2-linux

COPY requirements.txt /opt/app

WORKDIR /opt/app

RUN apt-get update && \
    pip install --no-cache-dir --upgrade pip && \
    pip install -r requirements.txt

CMD ["cat", "/etc/os-release"]