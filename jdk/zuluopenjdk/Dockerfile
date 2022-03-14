FROM centos:centos7.9.2009

MAINTAINER utf7
ARG WORK_DIR=/opt/apps
ARG JDK_DOWNLOAD_LOCATION="https://cdn.azul.com/zulu/bin/zulu11.54.25-ca-jdk11.0.14.1-linux_x64.tar.gz"
ARG JDK_TAR=zulu11.54.25-ca-jdk11.0.14.1-linux_x64.tar.gz
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

ENV JAVA_HOME ${WORK_DIR}/zulu11.54.25-ca-jdk11.0.14.1-linux_x64
ENV PATH $JAVA_HOME/bin:$PATH
WORKDIR ${WORK_DIR}
