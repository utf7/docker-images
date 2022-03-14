FROM centos:centos7.9.2009

MAINTAINER utf7
ARG WORK_DIR=/opt/apps
ARG JDK_DOWNLOAD_LOCATION="https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz"
ARG JDK_TAR=openjdk-11.0.2_linux-x64_bin.tar.gz
RUN  \
    set -xeu && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    yum install -y vim lsof net-tools bind-utils && \
    yum -q clean all && \
    rm -rf /var/cache/yum && \
    mkdir -p ${WORK_DIR}/  && \
    chmod 755 ${WORK_DIR}/ && \
    curl ${JDK_DOWNLOAD_LOCATION} -o ${WORK_DIR}/${JDK_TAR} && \
    tar -C ${WORK_DIR} -xzf ${WORK_DIR}/${JDK_TAR} && \
    rm ${WORK_DIR}/${JDK_TAR}

ENV JAVA_HOME ${WORK_DIR}/jdk-11.0.2
ENV PATH $JAVA_HOME/bin:$PATH
WORKDIR ${WORK_DIR}
