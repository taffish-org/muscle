FROM ghcr.io/taffish-org/python:3.12.9

LABEL maintainer="taffish@163.com"

WORKDIR /root

RUN apt-get update && apt-get install -y curl git gcc g++ make

RUN curl -L -O https://github.com/rcedgar/muscle/archive/refs/tags/v5.3.tar.gz && tar -zxvf /root/v5.3.tar.gz && cd /root/muscle-5.3/src/ && \
    sed -i 's/asserta(sizeof(void \*) == 4);/asserta(sizeof(void \*) == 8);/g' myutils.cpp && \
    sh ./build_linux.bash && cp ../bin/muscle /usr/local/bin/

ENV TAFFISH_ENV=TAFFISH
ENV TAFFISH_NAME=muscle
