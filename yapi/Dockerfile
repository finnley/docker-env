FROM node:12-alpine

COPY repositories /etc/apk/repositories

# 安装构建工具
RUN apk add --update --no-cache ca-certificates curl wget cmake build-base git bash python make gcc g++ zlib-dev autoconf automake file nasm \
  && update-ca-certificates

RUN npm install -g yapi-cli --registry http://mirrors.cloud.tencent.com/npm/
# RUN npm install -g yapi-cli --registry https://registry.npm.taobao.org

EXPOSE 3000 9090