FROM ubuntu:22.04

LABEL MAINTAINER="me@ukto.top"

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:zh' LC_ALL='en_US.UTF-8' OS_VERSION=22.04

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends locales tzdata curl ca-certificates \
    && echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
    && locale-gen zh_CN.UTF-8 \
    && ln -fs /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && dpkg-reconfigure --frontend noninteractive tzdata \
    && find /var/lib/apt/lists -type f -delete \
    && find /var/cache -type f -delete \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/cache/* \
    && rm -rf /tmp/* \
    && apt-get purge \
    && apt-get autoremove \
    && apt-get clean