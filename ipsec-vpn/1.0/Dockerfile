# ipsec-vpn

FROM centos:7
ENV container docker
ENV VERSION 1.0
MAINTAINER Anyshpm Chen <anyshpm@anyshpm.com>

ARG BUILD_DATE
ARG VCS_REF
LABEL org.label-schema.build-date=$BUILD_DATE \
    org.label-schema.name="e.g. Example project name" \
    org.label-schema.description="Example project description in 300 chars or less" \
    org.label-schema.url="e.g. https://www.example.com/" \
    org.label-schema.vcs-ref=$VCS_REF \
    org.label-schema.vcs-url="e.g. https://github.com/microscaling/microscaling" \
    org.label-schema.vendor="e.g. ACME Inc" \
    org.label-schema.version=$VERSION \
    org.label-schema.schema-version="1.0"

COPY ./entrypoint.sh /usr/local/bin/
RUN yum install -y epel-release && \
    yum install -y xl2tpd libreswan openssl
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == \
    systemd-tmpfiles-setup.service ] || rm -f $i; done); \
    rm -f /lib/systemd/system/multi-user.target.wants/*;\
    rm -f /etc/systemd/system/*.wants/*;\
    rm -f /lib/systemd/system/local-fs.target.wants/*; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -f /lib/systemd/system/basic.target.wants/*;\
    rm -f /lib/systemd/system/anaconda.target.wants/*;
VOLUME ["/sys/fs/cgroup", "/lib/modules"]
EXPOSE 500/udp 4500/tcp
ENTRYPOINT "entrypoint.sh"
