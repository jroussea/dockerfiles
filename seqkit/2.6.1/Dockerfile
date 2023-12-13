# Image base
FROM ubuntu:22.04

# labels instruction

# updating and installing dependencies
RUN apt-get update && apt-get install -y wget

# seqkit download and creation of the /data directory which will contain the data for the analyzes
RUN wget "https://github.com/shenwei356/seqkit/releases/download/v2.6.1/seqkit_linux_amd64.tar.gz" -O seqkit.tar.gz && \
	tar zxvf seqkit.tar.gz && \
	mkdir seqkit_v2.6.1 && \
	mv seqkit /seqkit_v2.6.1 && \
	rm seqkit.tar.gz && \
	mkdir /data


ENV PATH="$PATH:/seqkit_v2.6.1"

# set /data as working directory
WORKDIR /data