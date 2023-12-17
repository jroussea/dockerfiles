FROM ubuntu:20.04

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    echo $TZ > /etc/timezone && \
    apt-get update -y && \
    apt-get install -y wget python3.8 python2.7 openjdk-11-jre-headless libpcre2-dev libgomp1 perl-doc curl && \
    ln -s /usr/bin/python3.8 /usr/bin/python3 && ln -s /usr/bin/python3.8 /usr/bin/python

WORKDIR /opt

RUN wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.65-97.0/alt/interproscan-core-5.65-97.0.tar.gz && \
    wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.65-97.0/alt/interproscan-core-5.65-97.0.tar.gz.md5 && \
    md5sum -c interproscan-core-5.65-97.0.tar.gz.md5 && \
    tar -zxf interproscan-core-5.65-97.0.tar.gz && \
    rm interproscan-core-5.65-97.0.tar.gz && \
    mv /opt/interproscan-5.65-97.0 /opt/interproscan

ENV PATH="/opt/interproscan:${PATH}"

WORKDIR /data
