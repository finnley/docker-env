ARG GO_VERSION
FROM golang:${GO_VERSION}

LABEL maintainer="Finnley <43@43.com>"

WORKDIR $GOPATH/src

RUN go env -w GO111MODULE=on && \
  go env -w GOPROXY=GOPROXY=https://goproxy.cn,direct

EXPOSE 8080 8088