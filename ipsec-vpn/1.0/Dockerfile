# trac

FROM alpine

MAINTAINER Anyshpm Chen <anyshpm@anyshpm.com>

ENV XL2TPD_VERSION="1.3.10" \
    WORKDIR="/opt/src"

RUN apk add --no-cache libreswan xl2tpd

COPY ./entrypoint.sh /usr/local/bin/

EXPOSE 500/udp 4500/tcp

VOLUME ["/lib/modules"]

ENTRYPOINT ["entrypoint.sh"]

CMD ["sleep", "3600"]
