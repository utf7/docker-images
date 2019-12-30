FROM centos:7.6.1810
MAINTAINER utf7

RUN yum install -y vim
RUN yum install -y net-tools
RUN yum install -y  bind-utils

RUN mkdir -p /jdk64
ADD jdk-8u231-linux-x64.tar.gz /jdk64/

ENV JAVA_HOME /jdk64/jdk1.8.0_231
ENV PATH $PATH:$JAVA_HOME/bin

WORKDIR /root/
