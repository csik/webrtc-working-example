FROM ubuntu:18.04

# Set up signaling server at localhost:9999

RUN mkdir /signaling
COPY ./ /signaling

RUN DEBIAN_FRONTEND="noninteractive" TZ="America/New_York" apt-get update && apt install -y software-properties-common 
RUN DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata

RUN         apt update && \
	apt-get install -y \
    sudo \
	curl \
    nano \
    python3.8 \
    python3-pip \
    python3.8-venv \ 
    python3.8-dev  && \
    apt-get -y autoremove && \
    rm -rf /var/lib/apt/lists/* && \
    python3.8 -m pip install -r /signaling/requirements.txt

EXPOSE 9999

CMD python3.8 /signaling/server.py & sleep infinity
