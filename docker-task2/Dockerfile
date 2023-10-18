FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
	cmake \
	make \
	python3 \
	python3-pip \
	libboost-all-dev \
	git \
	g++ \
	&& apt-get clean

RUN useradd -rm -d /home/fatimah -s /bin/bash -g root -G sudo -u 1001 fatimah
USER fatimah

WORKDIR /home/fatimah

CMD g++ -o cpp_app main.cpp;./cpp_app
