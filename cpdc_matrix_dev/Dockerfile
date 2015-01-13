FROM centos
MAINTAINER xiaotian.wu@chinacache.com
RUN yum install -y wget
RUN wget http://downloads.mesosphere.io/master/centos/7/mesos-0.21.0-py2.7-linux-x86_64.egg
RUN wget --no-check-certificate https://bootstrap.pypa.io/ez_setup.py
RUN python ez_setup.py --insecure
RUN easy_install mesos-0.21.0-py2.7-linux-x86_64.egg
RUN easy_install kazoo
RUN yum install -y gcc
RUN yum install -y python-devel
RUN easy_install rbtree
RUN yum install -y git
RUN yum install -y vim
RUN yum install -y subversion-devel
ENV PYTHONPATH /coding/matrix
RUN easy_install flask
