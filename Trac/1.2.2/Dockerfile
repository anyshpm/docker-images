# trac

FROM alpine

MAINTAINER Anyshpm Chen <anyshpm@anyshpm.com>

ENV VERSION="1.2.2" \
    TRACHOME="/var/www/trac"

RUN apk add --no-cache trac && \
    mkdir -p /var/www/trac && \
    touch /var/www/trac/.htpasswd

VOLUME "$TRACHOME"

EXPOSE 80

WORKDIR "$TRACHOME"

CMD tracd -e /var/www/trac -b 0.0.0.0 -p 80 --pidfile=/var/run/tracd.pid --basic-auth="*,.htpasswd,trac"
