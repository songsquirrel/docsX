## 安装

1. docker 安装ELK

    1.1. elasticsearch

```shell
# 拉取镜像
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.11.1
# 运行
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.11.1
```

[cluster install doc](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)

1.2. kabana

```shell
docker pull docker.elastic.co/kibana/kibana:7.11.1

docker run --link YOUR_ELASTICSEARCH_CONTAINER_NAME_OR_ID:elasticsearch -p 5601:5601 docker.elastic.co/kibana/kibana:7.11.1
```

​	[detail install doc](https://www.elastic.co/guide/en/kibana/current/docker.html)

1.3 logtash

```shell
docker pull docker.elastic.co/logstash/logstash:7.11.1


```

[detail config doc](https://www.elastic.co/guide/en/logstash/current/docker-config.html#docker-bind-mount-settings)



## 增删改查

1. 新增

    PUT/POST请求