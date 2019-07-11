FROM ubuntu:xenial

LABEL maintainer yzy<jimmy_777@126.com>

#RUN echo "deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main multiverse restricted universe" >> /etc/apt/sources.list
COPY sources.list /etc/apt/sources.list
RUN apt-get update && apt-get install -yqq nginx
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80 443

CMD /usr/sbin/nginx

