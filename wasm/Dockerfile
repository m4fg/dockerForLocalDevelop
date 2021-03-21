FROM ubuntu:18.04

RUN set -x && \
    apt-get -y update && \
    apt-get -y install cmake python2.7 python3 curl unzip git && \
    cd / && \
    git clone https://github.com/emscripten-core/emsdk

ADD ./entrypoint /entrypoint

ENTRYPOINT /entrypoint
VOLUME /built