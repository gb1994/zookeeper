FROM centos:centos7

RUN yum install -y wget

RUN mkdir /opt/confd

WORKDIR /opt/confd

RUN wget https://github.com/kelseyhightower/confd/releases/download/v0.16.0/confd-0.16.0-linux-amd64

RUN mkdir -p /opt/confd/bin && \
    mv confd-0.16.0-linux-amd64 /opt/confd/bin/confd && \
    chmod +x /opt/confd/bin/confd && \
    mkdir -p /etc/confd/conf.d/  && \
    export PATH="$PATH:/opt/confd/bin"

ADD   myconfig.toml  /etc/confd/conf.d/myconfig.toml

WORKDIR /opt/confd/bin

