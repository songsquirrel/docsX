[Docker Docs](https://docs.docker.com/get-started/)



### demo

1. define a container with dockerfile
2. build a image
```shell
docker build -f ${Dockerfile} -t ${imageName}:${imageVersion} .
```

3 . save a images

```shell
docker save -o ${fileName} ${imageID/tag}
```

3. run image as a container
> docker run --publish 8000:8080 --detach bb ${imageName}:${imageVersion}
> --publish asks Docker to forward traffic incoming on the host’s port 8000, to the container’s port 8080. Containers have their own private set of ports, so if you want to reach one from the network, you have to forward traffic to it in this way. Otherwise, firewall rules will prevent all network traffic from reaching your container, as a default security posture.
> --detach asks Docker to run this container in the background.
> --name specifies a name with which you can refer to your container in subsequent commands, in this case bb.
4. remove/stop a running container
    docker rm --force bb/docker stop bb

5. 删除容器

  docker rm -f {containerID}

6. 导出/导入容器快照

    docker export {containerID} > fileName.tar

    docker import $URL/PATH  [repository[:tag]]

7. 进入容器命令

    ```shell
    # 退出会导致容器终止
    docker attach $containerID
    # 退出容器仍会继续运行
    docker exec -it $containerID /bin/bash
    ```




## Docker 容器数据卷

容器数据持久化, 容器间数据共享.

实现方式: 

> 使用命令挂载
>
> ```shell
> # ro: 只读; rw: 读写;
> docker run -it -d -v ${主机目录}:${docker容器目录}:ro
> ```
>
> 具名挂载: 起名, 方便查找 docker volume
>
> 匿名挂载:
>
> 所有docker容器的卷, 没有指定主机目录的情况下, 均放在/var/lib/docker/volumes/XXX/_data

容器间的数据共享:

--volume-from

## Dockerfile 

EXPOSE : 声明镜像需要使用的端口, 方便使用者阅读, 不能映射端口到宿主机.