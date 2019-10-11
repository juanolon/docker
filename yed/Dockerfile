FROM openjdk:slim

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

ENV VERSION 3.17.1
ENV ARCH 64

RUN apt-get update && apt-get install curl gzip -y \
    && curl -L http://www.yworks.com/resources/yed/demo/yEd-${VERSION}_${ARCH}-bit_setup.sh -o /tmp/setup.sh \
    && chmod +x /tmp/setup.sh

# RUN /tmp/setup.sh

ENV USERNAME yed
RUN useradd -ms /bin/sh -u 1000 $USERNAME && \
    echo $USERNAME:$USERNAME | chpasswd && \
    echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN chown yed:yed /tmp/setup.sh && echo $USERNAME && mv /tmp/setup.sh /home/$USERNAME/setup.sh

USER $USERNAME
WORKDIR /home/$USERNAME

# ENTRYPOINT [ "java", "-jar", "/app/plantuml.jar" ]
# CMD [ "-h" ]
ENTRYPOINT ["/bin/bash"]
