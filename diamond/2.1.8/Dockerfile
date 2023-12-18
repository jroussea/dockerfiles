FROM ubuntu:20.04

WORKDIR /opt

RUN ln -snf /usr/share/zoneinfo/Europe/London /etc/localtime && \
	echo Europe/London > /etc/timezone && \
	apt-get update && apt-get install -y g++ automake cmake zlib1g-dev git libzstd-dev wget build-essential

RUN wget http://github.com/bbuchfink/diamond/archive/v2.1.8.tar.gz && \
	tar xzf v2.1.8.tar.gz && \
	cd diamond-2.1.8 && \
	mkdir bin && \
	cd bin && \
	cmake .. && \
	make -j4 && \
	make install

WORKDIR /data

ENV PATH="$PATH:/diamond-2.1.8"


