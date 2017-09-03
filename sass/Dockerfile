FROM alpine:3.1

RUN apk --update add git build-base make
RUN git clone https://github.com/sass/sassc
RUN cd sassc
RUN git clone https://github.com/sass/libsass
RUN SASS_LIBSASS_PATH=/sassc/libsass make

# install
RUN mv bin/sassc /usr/bin/sass

# cleanup
RUN cd / && rm -rf /sassc
RUN apk del git build-base
# sass binary still needs this because of dynamic linking.
RUN apk add libstdc++
RUN rm -rf /var/cache/apk/*

ENTRYPOINT [ "sass" ]
