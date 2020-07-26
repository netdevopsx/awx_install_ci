FROM ubuntu:18.04

RUN apt-get update && \
    apt-get -y install python3-pip

RUN pip3 install \
    ansible==2.9.6

RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.17.7/bin/linux/amd64/kubectl && \
    chmod +x ./kubectl \
    mv ./kubectl /usr/local/bin/kubectl