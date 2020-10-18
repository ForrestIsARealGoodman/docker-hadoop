FROM ubuntu:latest
MAINTAINER forrestisagoodman@gmail.com

ENV HADOOP_VERSION 3.3.0
ENV HADOOP_URL https://www.apache.org/dist/hadoop/common/hadoop-$HADOOP_VERSION/hadoop-$HADOOP_VERSION.tar.gz
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
ENV HADOOP_HOME=/usr/local/hadoop
ENV PATH=$PATH:/usr/local/hadoop/bin:/usr/local/hadoop/sbin

RUN apt-get update && \
    apt-get install -y openssh-server openjdk-8-jdk wget sudo -y && \
    ssh-keygen -t rsa -f ~/.ssh/id_rsa -P '' && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys && \
    service ssh start && \
    /usr/sbin/sshd -D && \
    wget HADOOP_URL && \
    mv hadoop-$HADOOP_VERSION.tar.gz /usr/local/hadoop && \
    rm hadoop-$HADOOP_VERSION.tar.gz && \
    rm /usr/local/hadoop/share/doc -rf



