FROM centos
MAINTAINER Xiaotian Wu <xiaotian.wu@chinacache.com>
RUN yum install -y wget
RUN wget http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
RUN yum localinstall -y mysql-community-release-el7-5.noarch.rpm
RUN yum install -y mysql-community-server
RUN echo "[mysqld]" > /etc/my.cnf
RUN echo "bind-address = 0.0.0.0" >> /etc/my.cnf
RUN echo "skip-name-resolve" >> /etc/my.cnf
RUN echo "init_file = /etc/my.init" >> /etc/my.cnf
RUN echo "GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;" > /etc/my.init
