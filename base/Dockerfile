FROM anapsix/alpine-java
MAINTAINER forrestisagoodman@gmail.com

ENV HADOOP_VERSION 3.3.0
ENV HADOOP_URL https://www.apache.org/dist/hadoop/common/hadoop-$HADOOP_VERSION/hadoop-$HADOOP_VERSION.tar.gz
ENV HADOOP_HOME=/usr/local/hadoop
ENV PATH=$PATH:/usr/local/hadoop/bin:/usr/local/hadoop/sbin

RUN apk update && \
    apk add --no-cache openssh-server wget openrc && \
    ssh-keygen -t rsa -f ~/.ssh/id_rsa -P '' && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys && \
    wget $HADOOP_URL && \
    mv hadoop-$HADOOP_VERSION.tar.gz /usr/local/hadoop && \
    rm /usr/local/hadoop/share/doc -rf



