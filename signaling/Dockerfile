FROM ubuntu:18.04

# Set up signaling server at localhost:9999

RUN mkdir /signaling
COPY ./ /signaling

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


RUN pip3 install -r /signaling/requirements.txt

EXPOSE 9999

CMD python3.9 /signaling/server.py & sleep infinity
