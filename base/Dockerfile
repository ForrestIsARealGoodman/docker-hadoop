FROM ubuntu:latest
MAINTAINER forrestisagoodman@gmail.com

ENV JDK8_URL packages/jdk-8u121-linux-x64.tar.gz
ENV JAVA_HOME /usr/local/jdk1.8.0_121
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar

ENV HADOOP_VERSION 3.3.0
ENV HADOOP_URL packages/hadoop-$HADOOP_VERSION.tar.gz
ENV HADOOP_HOME=/usr/local/hadoop-$HADOOP_VERSION
ENV PATH=$PATH:$JAVA_HOME/bin:/usr/local/hadoop/bin:/usr/local/hadoop/sbin

ADD $JDK8_URL /usr/local/
ADD $HADOOP_URL /usr/local

RUN apt-get update && \
    apt-get install openssh-server wget -y && \
    ssh-keygen -t rsa -f ~/.ssh/id_rsa -P '' && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys && \
    rm $HADOOP_HOME/share/doc -rf