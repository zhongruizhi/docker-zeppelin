FROM ruizhizhong058/spark-base:3.5.1-hadoop3.3.6
LABEL MAINTAINER="Ruizhi Zhong <ruizhi.zhong@zoom.us>"

ENV APACHE_SPARK_VERSION 3.5.1
ENV APACHE_HADOOP_VERSION 3.3.6
ENV ZEPPELIN_VERSION 0.11.0

RUN set -x \
    && curl -fSL -k "https://dlcdn.apache.org/zeppelin/zeppelin-${ZEPPELIN_VERSION}/zeppelin-${ZEPPELIN_VERSION}-bin-all.tgz" -o /tmp/zeppelin.tgz \
    && tar -xzvf /tmp/zeppelin.tgz -C /opt/ \
    && mv /opt/zeppelin-* /opt/zeppelin \
    && rm /tmp/zeppelin.tgz

ENV SPARK_SUBMIT_OPTIONS "--jars /opt/zeppelin/sansa-examples-spark-2016-12.jar"

WORKDIR /opt/zeppelin

CMD ["/opt/zeppelin/bin/zeppelin.sh"]
