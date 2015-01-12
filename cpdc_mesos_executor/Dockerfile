FROM centos
MAINTAINER xiaotian.wu@chinacache.com
RUN yum install -y wget
RUN wget http://downloads.mesosphere.io/master/centos/7/mesos-0.21.0-py2.7-linux-x86_64.egg
RUN wget --no-check-certificate https://bootstrap.pypa.io/ez_setup.py
RUN python ez_setup.py --insecure
RUN easy_install mesos-0.21.0-py2.7-linux-x86_64.egg
RUN yum install -y git
RUN yum install -y subversion-devel
RUN git clone https://github.com/xiaotianwu/mesos_docker_executor_0_2_2
RUN chmod +x /mesos_docker_executor_0_2_2/executor.py
ENTRYPOINT ["/mesos_docker_executor_0_2_2/executor.py"]
