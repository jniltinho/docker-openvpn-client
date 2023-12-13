FROM debian:12

## docker build -t jniltinho/openvpn-client https://github.com/jniltinho/docker-openvpn-client.git#:Debian
## docker run --rm -it --cap-add=NET_ADMIN --device=/dev/net/tun -v ${HOME}/.ssh/docker:/root/.ssh -v ${PWD}:/config jniltinho/openvpn-client bash
## openvpn --cd /config --config /config/vpn-ae.conf --daemon

## Add below Flags OpenVPN 2.4 in config
#script-security 2
#providers legacy default
#tls-cipher "DEFAULT:@SECLEVEL=2"
#data-ciphers AES-256-GCM:AES-128-GCM:BF-CBC
#data-ciphers-fallback BF-CBC


ENV TZ America/Sao_Paulo
ENV SHELL /bin/bash

WORKDIR /config

RUN mv /bin/sh /bin/sh.old && cp /bin/bash /bin/sh
COPY ./bashrc /root/.bashrc


RUN apt-get update && apt-get install -yq jq openvpn net-tools vim ssh iptables tzdata vim unzip \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/cache/apt/archive/*.deb

