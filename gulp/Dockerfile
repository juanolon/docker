FROM node:alpine

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

RUN npm install -g gulp-cli gulp

USER node
WORKDIR /home/node/build

ENTRYPOINT ["gulp"]
