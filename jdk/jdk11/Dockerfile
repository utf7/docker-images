FROM centos:centos7.9.2009


MAINTAINER yechao.chen

RUN  \
    set -xeu && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    yum install -y vim lsof net-tools bind-utils && \
    mkdir -p /opt/apps/  && \
    chmod 755 /opt/apps/ && \
    cd /opt/apps/ && \
    wget https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz /opt/apps/ && \
    tar -zxvf openjdk-11.0.2_linux-x64_bin.tar.gz && \
    rm -rf openjdk-11.0.2_linux-x64_bin.tar.gz

ENV JAVA_HOME /opt/apps/jdk-11.0.2
ENV PATH $JAVA_HOME/bin:$PATH
ENV LANG en_US.UTF-8
WORKDIR /opt/apps
