# Image base
FROM ubuntu:22.04

# updating and installing dependencies
RUN apt-get -y update && apt-get install -y wget build-essential zlib1g zlib1g-dev python3.10 sqlite3 python3-pip

WORKDIR /opt 

RUN wget https://github.com/eggnogdb/eggnog-mapper/archive/refs/tags/2.1.12.tar.gz &&  \
	tar xvf 2.1.12.tar.gz && \
	mv eggnog-mapper-2.1.12 eggnog-mapper && \
	cd /opt/eggnog-mapper && \
	pip install -r requirements.txt

WORKDIR /data

ENV PATH="/opt/eggnog-mapper:/opt/eggnog-mapper/eggnogmapper/bin:${PATH}"
