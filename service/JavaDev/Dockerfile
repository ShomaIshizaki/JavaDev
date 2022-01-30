FROM ubuntu

ARG TZ=Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt -y update && apt -y upgrade && \
	apt -y install tzdata vim openjdk-11-jdk maven
RUN useradd -s /bin/bash -m appuser && echo "appuser:appuser" | chpasswd
ADD . /home/appuser
WORKDIR /home/appuser
USER appuser
