FROM centos
MAINTAINER Xiaotian Wu <xiaotian.wu@chinacache.com>
RUN yum install -y wget
RUN yum install -y java
RUN yum install -y tar
RUN wget http://mirror.bit.edu.cn/apache/kafka/0.8.1.1/kafka_2.8.0-0.8.1.1.tgz
RUN tar -zxvf kafka_2.8.0-0.8.1.1.tgz
RUN rm -f /kafka_2.8.0-0.8.1.1/config/server.properties
RUN sed -e 's/export KAFKA_HEAP_OPTS="-Xmx1G -Xms1G"/export KAFKA_HEAP_OPTS="-Xmx16G -Xms16G"/' -i /kafka_2.8.0-0.8.1.1/bin/kafka-server-start.sh
EXPOSE 9092
ENV PATH $PATH:/kafka_2.8.0-0.8.1.1/bin
