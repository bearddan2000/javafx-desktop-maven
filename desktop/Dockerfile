FROM ubuntu:latest

# Replace 1000 with your user / group id
RUN sed 's/main$/main universe/' -i /etc/apt/sources.list && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends software-properties-common \
    && useradd -d /home/developer -m developer -s /bin/bash

ENV DISPLAY ":0"
ENV HOME /home/developer

USER developer
