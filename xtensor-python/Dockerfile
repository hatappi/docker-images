FROM ubuntu:16.04
MAINTAINER Yusaku Hatanaka (hatappi)

RUN apt-get update -y && \
    apt-get install -y \
    python3-dev python3-pip wget bzip2 cmake git

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

RUN pip3 install pytest
RUN git clone https://github.com/pybind/pybind11.git /usr/local/src/pybind11
RUN cd /usr/local/src/pybind11 && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make check -j 4

RUN /root/anaconda3/bin/conda install -y -c conda-forge xtensor-python
