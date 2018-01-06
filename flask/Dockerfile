FROM python:latest

RUN mkdir /workdir

RUN apt update && apt install -y vim \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir \
ipython \
pillow \
requests \
flask \
pyyaml

WORKDIR /workdir
