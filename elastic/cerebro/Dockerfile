FROM --platform=linux/amd64 ubuntu:latest

RUN apt-get install
RUN apt-get update
RUN apt-get install wget -y sudo
RUN apt-get install openjdk-17-jdk

RUN useradd -ms /bin/bash cerebro
USER cerebro
WORKDIR /home/cerebro

RUN wget https://github.com/lmenezes/cerebro/releases/download/v0.9.4/cerebro-0.9.4.zip
RUN unzip cerebro-0.9.4.zip
RUN ln -s cerebro-0.9.4 cerebro

CMD [ "./cerebro/bin/cerebro" ]