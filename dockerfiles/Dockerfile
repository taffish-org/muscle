FROM ghcr.io/taffish-org/debian:12

LABEL maintainer="taffish@163.com"

WORKDIR /root

COPY . .

RUN apt-get update && apt-get install -y curl gcc g++ make git python3

RUN curl -L -O https://github.com/rcedgar/muscle/archive/refs/tags/v5.3.tar.gz && tar -zxvf v5.3.tar.gz && cd muscle-5.3/src/ && sed -i 's/asserta(sizeof(void \*) == 4);/asserta(sizeof(void *) == 4 || sizeof(void \*) == 8);/g' myutils.cpp && sh ./build_linux.bash && cp ../bin/muscle /usr/local/bin/

ENV TAFFISH_ENV=TAFFISH
ENV TAFFISH_NAME=muscle
