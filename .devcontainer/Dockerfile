# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.224.3/containers/dotnet/.devcontainer/base.Dockerfile

# [Choice] .NET version: 6.0, 5.0, 3.1, 6.0-bullseye, 5.0-bullseye, 3.1-bullseye, 6.0-focal, 5.0-focal, 3.1-focal
ARG VARIANT="6.0-bullseye-slim"
FROM mcr.microsoft.com/vscode/devcontainers/dotnet:0-${VARIANT}

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1

RUN sudo apt update
RUN sudo apt install libgtk-3-dev -y

RUN wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN sudo dpkg -i packages-microsoft-prod.deb

RUN sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1 && \
  sudo apt-get install -y dotnet-sdk-5.0

RUN sudo apt install -y xauth coreutils gawk
USER vscode
RUN echo ~/.Xauthority
RUN magiccookie=$(echo 'password'|tr -d '\n\r'|md5sum|gawk '{print $1}') && xauth add host.docker.internal:0 . $magiccookie
ENV DISPLAY=host.docker.internal:0 