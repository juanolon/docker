FROM node:alpine

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

RUN npm install -g less

# ENV USERNAME lessc
# RUN adduser -D -u 1000 $USERNAME && \
#     echo $USERNAME:$USERNAME | chpasswd && \
#     echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER node
WORKDIR /home/node/build

ENTRYPOINT ["lessc"]
