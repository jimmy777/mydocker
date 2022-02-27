
# redis
docker run --name redis \
--privileged=true \
-p 6379:6379 \
-v $PWD/etc/redis.conf:/etc/redis/redis.conf \
-v $PWD/data:/data \
-d redis:5.0.13 redis-server /etc/redis/redis.conf --appendonly yes


# 不挂载配置文件： 
docker run --name redis -p 6379:6379 -d --restart=always redis redis-server --appendonly yes --requirepass "这是密码"
