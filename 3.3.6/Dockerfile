FROM haozhonghu/ubuntu:14.04

MAINTAINER Gavin Hu <haozhonghu@hotmail.com>

LABEL name="zookeeper" version="3.3.6"

RUN wget http://mirrors.cnnic.cn/apache/zookeeper/zookeeper-3.3.6/zookeeper-3.3.6.tar.gz -O /opt/zookeeper-3.3.6.tar.gz \
    && tar -xzf /opt/zookeeper-3.3.6.tar.gz -C /opt \
    && mkdir -p /tmp/zookeeper

RUN echo 'tickTime=2000' >> /opt/zookeeper-3.3.6/conf/zoo.cfg \
    && echo 'initLimit=10' >> /opt/zookeeper-3.3.6/conf/zoo.cfg \
    && echo 'syncLimit=5' >> /opt/zookeeper-3.3.6/conf/zoo.cfg \
    && echo 'dataDir=/tmp/zookeeper' >> /opt/zookeeper-3.3.6/conf/zoo.cfg \
    && echo 'clientPort=2181' >> /opt/zookeeper-3.3.6/conf/zoo.cfg

EXPOSE 2181 2888 3888

WORKDIR /opt/zookeeper-3.3.6

VOLUME ["/opt/zookeeper-3.3.6/conf", "/tmp/zookeeper"]

ENTRYPOINT ["/opt/zookeeper-3.3.6/bin/zkServer.sh", "start-foreground"]
