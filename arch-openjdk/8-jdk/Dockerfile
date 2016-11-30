# meesong/openjdk:8-jdk

FROM meesong/archlinux:latest

MAINTAINER MeeSong <meesong@outlook.com>

ENV LANG=C.UTF-8

ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ENV JAVA_VERSION=8.u112

RUN { \
        echo '#!/bin/sh'; \
        echo 'set -e'; \
        echo; \
        echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; \
    } > /usr/local/bin/docker-java-home \
    && chmod +x /usr/local/bin/docker-java-home

RUN set -x \
    && pacman -Syu --noconfirm \
    && pacman -S --noconfirm jdk8-openjdk \
    && pacman -Scc --noconfirm \
    && [ "$JAVA_HOME" = "$(docker-java-home)" ]
