FROM alpine

MAINTAINER Ilio Catallo <info@iliocatallo.it>

ARG RANCHER_CLI_VERSION=v0.6.8
ARG DOCKER_VERSION=19.03.2

RUN apk add --no-cache ca-certificates openssh-client curl

# Install docker client
RUN curl -sSL https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz | tar -xz -C /usr/local/bin/ --strip-components=1 \
    && chmod +x /usr/local/bin/docker

# Install Rancher cli
RUN curl -sSL "https://github.com/rancher/cli/releases/download/${RANCHER_CLI_VERSION}/rancher-linux-amd64-${RANCHER_CLI_VERSION}.tar.gz" | tar -xz -C /usr/local/bin/ --strip-components=2 \
    && chmod +x /usr/local/bin/rancher

RUN apk del curl

WORKDIR /data

ENTRYPOINT ["rancher"]
