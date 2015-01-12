FROM cpdc/mesos_executor_0_2_2
MAINTAINER Xiaotian Wu <xiaotian.wu@chinacache.com>
RUN git clone https://github.com/xiaotianwu/walle_monitor_0_2
RUN git clone https://github.com/xiaotianwu/kafka-python
RUN cd kafka-python&&python setup.py install
ENV WALLE_MONITOR_PATH /walle_monitor_0_2
ENV PYTHONPATH /walle_monitor_0_2
