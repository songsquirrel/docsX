1. 拉取镜像

    ```shell
    docker pull rocketmqinc/rocketmq
    ```

    

    

2. 启动nameserver

    ```shell
    docker run -d -p 9876:9876 -v F:/data/namesrv/logs:/root/logs -v F:/data/namesrv/store:/root/store --
    name rmqnamesrv -e "MAX_POSSIBLE_HEAP=100000000" rocketmqinc/rocketmq sh mqnamesrv
    ```

    

3. 启动broker

    ```shell
    docker run -d -p 10911:10911 -p 10909:10909 -v F:/data/broker/logs:/root/logs -v F:/data/broker/store:/root/store --name rmqbroker --link rmqnamesrv:namesrv -e "NAMESRV_ADDR=namesrv:9876" -e "MAX_POSSIBLE_HEAP=200000000" rocketmqinc/rocketmq:4.5.0 sh mqbroker 
    ```

4. 安装控制台

    ``` shell
    docker pull styletang/rocketmq-console-ng
    docker run -e "JAVA_OPTS=-Drocketmq.namesrv.addr=127.0.0.1:9876 -Dcom.rocketmq.sendMessageWithVIPChannel=false" -p 8080:8080 -t styletang/rocketmq-console-ng
    
    ```



