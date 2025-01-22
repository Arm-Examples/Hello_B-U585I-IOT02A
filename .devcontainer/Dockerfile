FROM mcr.microsoft.com/devcontainers/universal:2 AS build

SHELL [ "/bin/bash", "-c" ]
WORKDIR /root

RUN . <(curl -L https://aka.ms/vcpkg-init.sh)

COPY vcpkg-configuration.json /root
COPY packlist.txt /root

RUN . ~/.vcpkg/vcpkg-init && \
    vcpkg-shell x-update-registry --all && \
    vcpkg-shell activate && \
    cpackget init https://www.keil.com/pack/index.pidx && \
    cpackget add -f packlist.txt

FROM mcr.microsoft.com/devcontainers/universal:2

RUN mkdir -p /codespace/.vcpkg/ && \
    chown -R codespace:codespace /codespace/.vcpkg && \
    mkdir -p /codespace/.cache/arm/packs/ && \
    chown -R codespace:codespace /codespace/.cache

COPY --from=build --chown=codespace:codespace /root/.vcpkg/downloads /codespace/.vcpkg/
COPY --from=build --chown=codespace:codespace /root/.cache/arm/packs/.Download /codespace/.cache/arm/packs/
