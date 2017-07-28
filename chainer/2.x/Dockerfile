FROM ubuntu:16.04
MAINTAINER Yusaku Hatanaka (hatappi)

RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    python3-dev \
    python3-pip && \
    rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*

RUN pip3 install setuptools

RUN pip3 install \
  'chainer>=2.0.0,<3.0.0'
