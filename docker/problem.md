## docker 容器间网络访问

方式1: 创建bridge网络

```shell
# 创建bridge网络
docker network create {network name}
# 查询网络
docker network ls
# 运行容器时连接到指定网络
docker run -it --name <containerName> --network <bridgeName> --network-alias <网络别名,相当于域名>  <image:version>
# docker run -it --name gateway --network hclp --network-alias gateway gateway:1.0
```



## docker指定配置文件启动redis

```shell
docker run -v /myredis/conf/redis.conf:/usr/local/etc/redis/redis.conf --name myredis redis redis-server /usr/local/etc/redis/redis.conf
```

## docker镜像共享宿主机环境,以减少镜像体积.



## Docker启动centos systemctl报错

```shell
# --privileged 以特权模式启动
docker run -it -d -p 10022:22 --name main-centos --privileged centos:7.8.2003 /usr/sbin/init
```



