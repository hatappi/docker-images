FROM ubuntu:16.04
MAINTAINER Yusaku Hatanaka (hatappi)

RUN apt-get update -y && \
    apt-get install -y \
    python3-dev wget bzip2

RUN apt-get install apt-file -y && \
    apt-file update && \
    apt-file search add-apt-repository && \
    apt-get install software-properties-common  -y

RUN add-apt-repository ppa:ubuntu-toolchain-r/test && \
    apt-get update && \
    apt-get install g++-7 -y

RUN wget https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh && \
    bash Anaconda3-4.4.0-Linux-x86_64.sh -b

RUN /root/anaconda3/bin/conda install -y -c conda-forge xtensor
