FROM alpine:3.3

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

RUN mkdir /graphviz && \
  apk add --update graphviz font-bitstream-type1 ghostscript-fonts wget tar xz && \
  rm -rf /var/cache/apk/*

RUN wget http://cdsoft.fr/pp/pp-linux-x86_64.txz

RUN tar -xvf pp-linux-x86_64.txz && \
    mv pp /usr/local/bin/pp

WORKDIR /files

ENTRYPOINT ["pp"]
