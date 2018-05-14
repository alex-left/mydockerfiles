FROM python:3-stretch

RUN mkdir /workdir

RUN apt update && apt install -y vim less \
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
