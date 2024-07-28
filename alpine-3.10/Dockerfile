FROM alpine:3.10

LABEL MAINTAINER="me@ukto.top"

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:zh' LC_ALL='en_US.UTF-8'

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk update && apk add --no-cache bash tzdata curl && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime