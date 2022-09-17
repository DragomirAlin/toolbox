FROM ubuntu:20.04

WORKDIR /project
VOLUME /project

ARG TERRAFORM_VERSION

RUN apt-get update && apt-get install --no-install-recommends -y \
 python3.9 \
 python3.9-dev \
 python3.9-venv \
 python3-pip \
 wget \
 unzip 

# Terraform
RUN wget -O /usr/bin/terraform_${TERRAFORM_VERSION}_linux_amd64.zip https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip
RUN unzip /usr/bin/terraform_${TERRAFORM_VERSION}_linux_amd64.zip -d /usr/bin \
     && rm -f /usr/bin/terraform_${TERRAFORM_VERSION}_linux_amd64.zip