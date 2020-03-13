FROM ubuntu:16.04

USER root
RUN apt-get update
RUN apt-get install \
	git \
	rsync \
	sudo \
	wget \
	x11-xserver-utils \
	ca-certificates \
	-y --no-install-recommends

RUN useradd -m ue4
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers && \ 
	adduser ue4 sudo 

USER ue4
RUN cd /home/ue4 && \
	git clone --progress https://github.com/taimir/AirSim.git && \
	cd AirSim && \
	./setup.sh && \
	./build.sh

WORKDIR /home/ue4
