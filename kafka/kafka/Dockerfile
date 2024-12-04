FROM --platform=linux/amd64 ubuntu:latest

RUN apt-get install
RUN apt-get update
RUN apt-get install wget -y sudo
RUN apt-get install -y openjdk-8-jdk

RUN useradd -ms /bin/bash kafka
USER kafka
WORKDIR /home/kafka

RUN wget https://archive.apache.org/dist/kafka/2.5.0/kafka_2.12-2.5.0.tgz
RUN tar xvf kafka_2.12-2.5.0.tgz
RUN ln -s kafka_2.12-2.5.0 kafka

COPY ./config/server.properties ./kafka/config/server.properites
ENV KAFKA_HEAP_OPTS="-Xmx400m -Xms400m"

RUN ./kafka/bin/zookeeper-server-start.sh -daemon config/zookeeper.properites

CMD [ "./kafka/bin/kafka-server-start.sh", "./kafka/config/server.properites" ]