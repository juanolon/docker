FROM python:3.6.1-slim

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

# http://damonlynch.net/rapid/download.html
RUN apt-get update && apt-get install -y \
    rapid-photo-downloader

ENV USERNAME rapid
RUN useradd -ms /bin/sh -u 1000 $USERNAME && \
    echo $USERNAME:$USERNAME | chpasswd && \
    echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER $USERNAME
WORKDIR /home/$USERNAME

ENTRYPOINT ["rapid-photo-downloader"]
