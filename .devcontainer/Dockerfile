FROM mcr.microsoft.com/devcontainers/universal:2-linux

WORKDIR /opt/app

COPY requirements.txt /opt/app

RUN apt-get update && \
    pip install --no-cache-dir --upgrade pip && \
    pip install -r requirements.txt

# Uses "agnoster" theme (original Oh My Zsh theme), with no plugins
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.2.1/zsh-in-docker.sh)" -- \
    -t agnoster

CMD ["cat", "/etc/os-release"]
