# FROM: https://hub.docker.com/r/bmennis/stringtie/dockerfile
# AND https://github.com/biotoolsdx/docker-stringtie/blob/master/Dockerfile

# FROM ubuntu:18.04
FROM ubuntu:23.04

# STRINGTIE VERSIONS ARE AT:
# http://ccb.jhu.edu/software/stringtie/dl/

ARG version=2.2.1
RUN mkdir -p /opt/tools

RUN \
  apt-get update && apt-get -y upgrade && apt-get install -y build-essential make git wget zlib1g-dev libbz2-dev && \
  wget -c http://ccb.jhu.edu/software/stringtie/dl/stringtie-${version}.Linux_x86_64.tar.gz && \
  tar -zxvf stringtie-${version}.Linux_x86_64.tar.gz && \
  cp stringtie-${version}.Linux_x86_64/stringtie /usr/local/bin && \
  rm -rf stringtie* && \
  apt-get remove --purge --yes \
              wget && \
  apt-get autoremove --purge --yes && \
  apt-get clean
  
