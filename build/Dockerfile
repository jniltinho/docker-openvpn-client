FROM alpine:3.17

RUN apk add --no-cache bash bind-tools iptables ip6tables openvpn

ENV TZ America/Sao_Paulo
ENV SHELL /bin/bash

COPY . /usr/local/bin

ENV KILL_SWITCH=on

ENTRYPOINT [ "entry.sh" ]
