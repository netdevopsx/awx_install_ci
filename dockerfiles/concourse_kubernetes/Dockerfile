FROM ubuntu:18.04
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get -y install \
    --no-install-suggests \
    apt-transport-https \
    gnupg2 \
    curl
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - && \
    echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | tee -a /etc/apt/sources.list.d/kubernetes.list
RUN curl -s https://helm.baltorepo.com/organization/signing.asc | apt-key add - && \
    echo "deb https://baltocdn.com/helm/stable/debian/ all main" | tee /etc/apt/sources.list.d/helm-stable-debian.list
RUN apt-get update
RUN apt-get -y install \
    --no-install-suggests \
    python3-pip \
    python3-setuptools \
    python3-wheel \
    kubectl=1.17.7-00 \
    helm=3.2.4-1 \
    git \
    jq && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install \
    ansible==2.9.10 \
    kubernetes \
    openshift \
    yq