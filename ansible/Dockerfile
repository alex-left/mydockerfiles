FROM python:2-stretch
ARG ansible_version=2.5.2
RUN mkdir /workdir

RUN apt purge -y python* && \
    rm -rf /usr/bin/python

RUN ln -s /usr/local/bin/python /usr/bin/python

RUN pip install --no-cache-dir \
    ansible==${ansible_version} \
    boto \
    boto3 \
    docker-py \
    mysql-connector-python \
    psycopg2

RUN mkdir /root/.aws

WORKDIR /workdir
