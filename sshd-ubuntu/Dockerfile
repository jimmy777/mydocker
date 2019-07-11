FROM ubuntu

MAINTAINER yzy<jimmy_777@126.com>

COPY ./sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install --no-install-recommends --no-install-suggests -yqq tzdata openssh-server \
    && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /var/run/sshd /root/.ssh
RUN sed -ri 's/session required pam_loginuid.so/#session required pam_loginuid.so/g' /etc/pam.d/sshd

ADD authorized_keys /root/.ssh/authorized_keys
ADD run.sh /run.sh
RUN chmod 755 /run.sh

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata

EXPOSE 22

CMD ["/run.sh"]

