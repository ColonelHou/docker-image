FROM centos
MAINTAINER Xiaotian Wu <xiaotian.wu@chinacache.com>
RUN yum install -y wget
RUN yum install -y java
RUN yum install -y tar
RUN wget http://mirror.bit.edu.cn/apache/kafka/0.8.1.1/kafka_2.8.0-0.8.1.1.tgz
RUN tar -zxvf kafka_2.8.0-0.8.1.1.tgz
RUN sed -e 's/export KAFKA_HEAP_OPTS="-Xmx1G -Xms1G"/export KAFKA_HEAP_OPTS="-Xmx16G -Xms16G"/' -i /kafka_2.8.0-0.8.1.1/bin/kafka-server-start.sh
EXPOSE 9092
ENV PATH $PATH:/kafka_2.8.0-0.8.1.1/bin:
RUN yum install -y net-tools
RUN echo -e "#!/bin/sh\nexport LOCAL_IP=\`ifconfig | grep \"255.255.255.128\" |  cut -f 2 -d \":\" | cut -f 10 -d \" \"\`&&echo -e \"\
broker.id=\$1\\\n\
port=9092\\\n\
advertised.host.name=\$LOCAL_IP\\\n\
num.network.threads=2\\\n\
num.io.threads=8\\\n\
socket.send.buffer.bytes=1048576\\\n\
socket.receive.buffer.bytes=1048576\\\n\
socket.request.max.bytes=104857600\\\n\
log.dirs=/root/cpdc/kafka\\\n\
num.partitions=2\\\n\
log.retention.hours=48\\\n\ 
log.segment.bytes=536870912\\\n\
log.retention.check.interval.ms=60000\\\n\
log.cleaner.enable=false\\\n\
auto.leader.rebalance.enable=true\\\n\
zookeeper.connect=223.202.46.151:2181,223.202.46.152:2181,223.202.46.153:2181/YRFS/BJ-TONGZHOU/DockerTest\\\n\
zookeeper.connection.timeout.ms=1000000\" > /kafka_2.8.0-0.8.1.1/config/server.properties&&/kafka_2.8.0-0.8.1.1/bin/kafka-server-start.sh /kafka_2.8.0-0.8.1.1/config/server.properties" > /create_config_and_launch.sh
RUN chmod +x /create_config_and_launch.sh
ENTRYPOINT ["/create_config_and_launch.sh"]
