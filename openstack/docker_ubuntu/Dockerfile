FROM ubuntu:20.04

WORKDIR /project
VOLUME /project

RUN apt-get update && apt-get install --no-install-recommends -y \
 python3.9 \
 python3.9-dev \
 python3.9-venv \
 python3-pip \
 wget \
 unzip

# OpenStack CLI
RUN pip install python-openstackclient

ENTRYPOINT ["bash", "entrypoint.sh"]