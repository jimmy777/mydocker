FROM dlyle65535/centos:6
MAINTAINER David Lyle

ADD ambari.repo /etc/yum.repos.d/
RUN yum install -y ambari-server
RUN ambari-server setup -s

EXPOSE 8080
CMD ambari-server start && tail -F /var/log/ambari-server/ambari-server.log 
