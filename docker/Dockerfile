ARG UBUNTU_VERSION=24.04

FROM ubuntu:${UBUNTU_VERSION}

ARG GROUP=user
ARG GROUP_ID=1000
ARG TIMEZONE=Europe/Berlin
ARG USER=user
ARG USER_ID=1000

RUN set -e -u -x; \
    apt-get update; \
    apt-get install --no-install-recommends --yes less nano tzdata; \
    rm --force --recursive  /var/lib/apt/lists/*

RUN set -e -u -x; \
    userdel --remove ubuntu; \
    groupadd --gid ${GROUP_ID} ${GROUP}; \
    useradd --create-home --gid ${GROUP} --home-dir /home/${USER} --shell /bin/bash --uid ${USER_ID} ${USER}; \
    chown --recursive ${USER}:${USER} /home/${USER}; \
    chmod --recursive 0750 /home/${USER}

COPY docker/entrypoint.sh /usr/local/bin

ENTRYPOINT ["entrypoint.sh"]
