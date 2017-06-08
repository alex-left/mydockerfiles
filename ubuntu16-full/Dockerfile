
FROM ubuntu:xenial

ENV PASSROOT test

# Delete not essentials systemd units
RUN find /etc/systemd/system \
         /lib/systemd/system \
         -path '*.wants/*' \
         -not -name '*journald*' \
         -not -name '*systemd-tmpfiles*' \
         -not -name '*systemd-user-sessions*' \
         -exec rm \{} \;

RUN printf "LANG=en_US.UTF-8\nLC_ALL=en_US.UTF-8\nLANG=en_US.UTF-8\n" > /etc/default/locale

RUN systemctl set-default multi-user.target

RUN apt-get update && apt-get install -y \
    ssh \
    python \
    apt-transport-https \
    software-properties-common \
    curl \
    wget \
    language-pack-en \
    language-pack-es \
    sudo \
		rsync \
    git \
    vim && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

RUN sed -i s/prohibit-password/yes/g /etc/ssh/sshd_config && \
    echo "root:${PASSROOT}" | chpasswd

RUN useradd -ms /bin/bash ubuntu

CMD ["/sbin/init"]


# docker run -dit -P --cap-add=SYS_ADMIN -v /sys/fs/cgroup:/sys/fs/cgroup:ro ubuntu16-full
# https://github.com/solita/docker-systemd
