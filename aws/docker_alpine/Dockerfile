FROM alpine

WORKDIR /project

VOLUME /project

# Add repo modules
RUN apk add --no-cache \
    python3 \
    py3-pip \
    py3-setuptools \
    ca-certificates \
    bash \
    gcc \
    openssh \
    openssh-client \
    musl-dev \
    linux-headers \
    libffi-dev \
    jq

# AWS CLI Python 3
RUN pip3 install --upgrade pip awscli boto3 \
    && echo "complete -C '/usr/bin/aws_completer' aws" >> ~/.bashrc \
    && ln -s /usr/bin/python3 /usr/bin/python