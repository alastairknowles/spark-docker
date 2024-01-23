FROM amazonlinux:2023.3.20240117.0

RUN yum install -y wget which tar gzip procps hostname rsync unzip vim java-17-amazon-corretto-headless

RUN wget https://dlcdn.apache.org/spark/spark-3.3.4/spark-3.3.4-bin-hadoop3-scala2.13.tgz \
    && tar -xvf spark-3.3.4-bin-hadoop3-scala2.13.tgz \
    && mv spark-3.3.4-bin-hadoop3-scala2.13 /opt/spark \
    && rm spark-3.3.4-bin-hadoop3-scala2.13.tgz

ENV JDK_JAVA_OPTIONS="\
--add-opens=java.base/sun.nio.ch=ALL-UNNAMED \
--add-opens=java.base/sun.nio.cs=ALL-UNNAMED \
--add-opens=java.base/sun.security.action=ALL-UNNAMED \
--add-opens=java.base/sun.util.calendar=ALL-UNNAMED \
--add-opens=java.base/java.time=ALL-UNNAMED \
--add-opens=java.base/java.lang=ALL-UNNAMED \
--add-opens=java.sql/java.lang.sql=ALL-UNNAMED \
--add-opens=java.base/java.lang.invoke=ALL-UNNAMED \
--add-opens=java.base/java.lang.reflect=ALL-UNNAMED \
--add-opens=java.base/java.io=ALL-UNNAMED \
--add-opens=java.base/java.nio=ALL-UNNAMED \
--add-opens=java.base/java.net=ALL-UNNAMED \
--add-opens=java.base/java.util=ALL-UNNAMED \
--add-opens=java.base/java.util.concurrent=ALL-UNNAMED \
--add-opens=java.base/java.util.concurrent.atomic=ALL-UNNAMED \
--add-opens=java.security.jgss/sun.security.krb5=ALL-UNNAMED"

ENV SPARK_HOME=/opt/spark
ENV PATH=$PATH:$SPARK_HOME/bin
ENV SPARK_NO_DAEMONIZE=true