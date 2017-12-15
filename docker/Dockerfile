FROM debian:latest
MAINTAINER domcomte

# shell to start from Kitematic
ENV DEBIAN_FRONTEND=noninteractive
ENV SHELL=/bin/bash

# install dependencies
RUN apt-get update && \
    apt-get install -y \
      asciidoc \
      docbook \
      docbook-xsl \
      dblatex \
      git \
      zip \
    && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /root

CMD cd /root && git clone https://github.com/sonatype/maven-example-en.git && cd mvn-example-en && ./build.sh -f pdf,chunked,epub,html
