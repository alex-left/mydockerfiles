FROM python:latest

RUN mkdir /workdir

RUN apt update && apt install -y vim \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir \
ipython \
psutil \
sympy \
numpy \
pillow \
requests \
pyyaml \
colorama \
passlib \
cryptography \
matplotlib \
pandas \
boto3

WORKDIR /workdir
