FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y install \
    --no-install-recommends \
    python3-pip \
    python3-setuptools \
    python3-wheel && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install \
    ansible==2.9.10 \
    jmespath \
    requests