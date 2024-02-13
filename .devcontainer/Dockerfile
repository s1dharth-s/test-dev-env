FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    apt-get install -y git && \
    add-apt-repository -y ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install --no-install-recommends -y python3.10 python3.10-dev python3.10-venv python3-pip python3-wheel build-essential && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    python3.10 -m pip install setuptools

COPY requirements.txt requirements.txt
COPY .pre-commit-config.yaml .pre-commit-config.yaml
RUN python3.10 -m pip install --upgrade pip
