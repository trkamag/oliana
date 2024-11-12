FROM mcr.microsoft.com/devcontainers/universal:2-linux

WORKDIR /opt/app

COPY requirements.txt /opt/app

RUN apt-get update && \
    pip install --no-cache-dir --upgrade pip && \
    pip install -r requirements.txt

ARG USERNAME=oliana
ARG USER_UID=1001
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

RUN sudo chmod 666 /var/run/docker.sock
# Add information to avoid failure of vscode docker extension
#RUN groupadd docker \
#    && usermod -aG docker $USER


# [Optional] Set the default user. Omit if you want to keep the default as root.
USER $USERNAME

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

CMD ["zsh"]
