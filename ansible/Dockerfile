FROM python:2
ARG ansible_version=2.3.2
RUN mkdir /workdir

RUN pip install --no-cache-dir \
    ansible==${ansible_version} \
    boto \
    boto3

RUN mkdir /root/.aws

WORKDIR /workdir
