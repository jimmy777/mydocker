# mysql-8.0.*


```
docker run --name mysql8 \
-e MYSQL_ROOT_PASSWORD=root \
-p 3306:3306 \
-v $PWD/data:/var/lib/mysql \
-v $PWD/log:/var/log/mysql \
-v $PWD/etc/my.cnf:/etc/mysql/my.cnf:rw \
-d mysql:8.0.28
```



# mysql-5.7.*
## my.cnf
```
[client]
default-character-set=utf8
 
[mysql]
default-character-set=utf8
 
[mysqld]
init_connect='SET collation_connection = utf8_unicode_ci'
init_connect='SET NAMES utf8'
character-set-server=utf8
collation-server=utf8_unicode_ci
skip-character-set-client-handshake
```

