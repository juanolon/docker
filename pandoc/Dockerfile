FROM haskell:8.4

MAINTAINER Juan Pablo Stumpf <juanolon@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

RUN sed -i "s#deb http://deb.debian.org/debian stretch main#deb http://deb.debian.org/debian stretch main contrib non-free#g" /etc/apt/sources.list

RUN apt-get update && \
    apt-get install --yes --no-install-recommends \
    texlive-latex-base \
    texlive-latex-recommended \
    texlive-latex-extra \
    texlive-fonts-recommended \
    pandoc-citeproc \
    wget \
    make \
    xz-utils \
    texlive-xetex \
    tex-gyre \
    ttf-mscorefonts-installer \
    python3 python3-dev \
    graphviz \
    fonts-texgyre lmodern texlive-fonts-extra \
    plantuml \
    unzip

RUN cabal update && cabal install \
    pandoc \
    pandoc-citeproc \
    pandoc-citeproc-preamble \
    pandoc-crossref \
    pandoc-filter-graphviz

RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py

RUN pip install pandoc-fignos pandoc-tablenos pandoc-plantuml-filter

ENV USERNAME docs
RUN useradd -ms /bin/sh -u 1000 $USERNAME && \
    echo $USERNAME:$USERNAME | chpasswd && \
    echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && \
    mkdir /docs && chown $USERNAME /docs

WORKDIR /home/$USERNAME/docs

# RUN /usr/local/bin/plantuml -testdot

# USER $USERNAME
VOLUME /home/$USERNAME/docs

ENTRYPOINT ["pandoc"]
