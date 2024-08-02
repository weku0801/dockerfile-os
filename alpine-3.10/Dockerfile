# 定义构建参数 OS_VERSION，默认值为 3.10
ARG OS_VERSION=3.10

# 使用 OS_VERSION 构建基础镜像
FROM alpine:${OS_VERSION}

LABEL MAINTAINER="me@ukto.top"

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:zh' LC_ALL='en_US.UTF-8'

# 使用国内镜像源加速
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
    apk update && \
    apk add --no-cache bash tzdata curl && \
    # 设置时区为上海
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apk del tzdata && \
    rm -rf /var/cache/apk/*