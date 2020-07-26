FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y apt-transport-https gnupg2 curl
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
RUN echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | tee -a /etc/apt/sources.list.d/kubernetes.list
RUN apt-get update
RUN apt-get -y install python3-pip kubectl=1.17.7-00

RUN pip3 install \
    ansible==2.9.6