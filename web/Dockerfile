FROM ubuntu:18.04

# Setup website gui on 7000

RUN mkdir /web
COPY ./ /web

RUN apt-get update && \
	apt-get install -y \
    sudo \
	curl \
    nano \
    python3.9-pip \
    python3.9-venv \ 
    python3.9-dev  && \
    apt-get -y autoremove && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 7000

WORKDIR /web/
CMD python3.9 -m http.server 7000 & sleep infinity
