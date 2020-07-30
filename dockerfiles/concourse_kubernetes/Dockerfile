FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y install python3-pip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install \
    ansible==2.9.8 \
    jmespath