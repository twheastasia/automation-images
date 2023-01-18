FROM ubuntu:22.04

# 使用镜像源、时区、中文
# ARG APT_MIRROR=xxx
# ARG APT_MIRROR=xxx
ENV TZ=Asia/Shanghai \
    LANG=zh_CN.UTF-8 \
    LANGUAGE=zh_CN.UTF-8:en_US.UTF-8:C.UTF-8 \
    SUPPORTED=zh_CN.UTF-8:en_US.UTF-8:C.UTF-8 \
    LC_ALL=zh_CN.UTF-8

ARG APT_MIRROR=mirrors.aliyun.com
RUN set -eux \
    &&  sed -i \
            -e "s|archive.ubuntu.com|${APT_MIRROR}|g" \
            -e "s|security.ubuntu.com|${APT_MIRROR}|g" \
        /etc/apt/sources.list \
    \
    && apt-get update -y --fix-missing \
    && apt-get install -y --no-install-recommends \
        apt-utils \
        tzdata \
        language-pack-zh-hans \
        locales \
    \
    && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone \
    \
    && localedef -i zh_CN -c -f UTF-8 -A /usr/share/locale/locale.alias zh_CN.UTF-8 \
    \
    && apt-get clean && apt-get autoclean && apt-get autoremove \
    && rm -rf /var/lib/apt/lists/*

# RUN apt-get -y update \
#     && apt-get install -y python python-pip openssh-client git vim \
#     && apt-get clean \
#     && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
