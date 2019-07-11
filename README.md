# docker

## tomcat
https://hub.docker.com/_/tomcat
```
# docker run -d -P --name tomcat tomcat:9.0.21-jdk8
```

## mysql
https://hub.docker.com/_/mysql

```
download
# docker pull mysql:5.7

run
# docker run -d -P --name mysql -e MYSQL_ROOT_PASSWORD=abcd1234 mysql:5.7

mysql-client 
# docker run -it --name mysqlclient --link mysql:mysql mysql:5.7 bash

...# mysql -hmysql -uroot -pabcd1234



```


# docker-compose

http://get.daocloud.io/#install-compose

```
# curl -L https://get.daocloud.io/docker/compose/releases/download/1.24.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose

# chmod +x /usr/local/bin/docker-compose

# docker-compose version
docker-compose version 1.24.1, build 4667896b
docker-py version: 3.7.3
CPython version: 3.6.8
OpenSSL version: OpenSSL 1.1.0j  20 Nov 2018
```






