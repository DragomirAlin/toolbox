FROM alpine

WORKDIR /project

VOLUME /project

ARG GCLOUD_VERSION

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

# GCloud
ADD https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-${GCLOUD_VERSION}-linux-x86_64.tar.gz /opt/
RUN tar zxf /opt/google-cloud-sdk-${GCLOUD_VERSION}-linux-x86_64.tar.gz -C /opt \
    && rm -f /opt/google-cloud-sdk-${GCLOUD_VERSION}-linux-x86_64.tar.gz \
    && ln -s /opt/google-cloud-sdk/bin/gcloud /usr/bin/ \
    && ln -s /opt/google-cloud-sdk/bin/gsutil /usr/bin/ \
    && echo "source /opt/google-cloud-sdk/completion.bash.inc" >> ~/.bashrc
