FROM php:7.1.5-alpine

RUN apk update && apk add bash

ENV USERNAME php
RUN adduser -D -u 1000 $USERNAME && \
    echo $USERNAME:$USERNAME | chpasswd && \
    echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER php
WORKDIR /home/php/src

ENTRYPOINT ["php", "-S", "0.0.0.0:8080"]
