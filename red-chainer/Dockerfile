FROM ubuntu:17.04
MAINTAINER Yusaku Hatanaka (hatappi)

ENV RUBY_VERSION 2.4.2

RUN apt-get update -y && \
    apt-get install -y wget git build-essential zlib1g-dev openssl libssl-dev

####################
#   Ruby Install   #
####################

RUN wget -O ruby.tar.gz https://cache.ruby-lang.org/pub/ruby/2.4/ruby-${RUBY_VERSION}.tar.gz && \
    mkdir /usr/src/ruby && \
    tar -zxvf ruby.tar.gz -C /usr/src/ruby --strip-components 1 && \
    rm ruby.tar.gz && \
    cd /usr/src/ruby && \
    ./configure && \
    make && \
    make install
  
####################
#   OpenBLAS       #
####################
RUN apt-get update -y && \
    apt-get install -y libopenblas-base libopenblas-dev


####################
#   Install Gem    #
####################
RUN gem install red-chainer numo-linalg && \
    ln -s `gem which chainer | sed -e "s/\/lib\/chainer.rb//g"`/examples /opt/examples

