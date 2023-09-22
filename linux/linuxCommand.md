1. linux常用命令安装

    ```shell
    # init
    yum install -y initscripts
    # netstat
    yum install -y net-tools
    # rz, sz
    yum install -y lrzsz
    # ssh
    yum install -y openssl openssh-server 
    ```

    

2. chown: 修改文件拥有者组

```shell
chown -R root:root *
# 将当前目录下所有文件用户设为root组root; -R指定目录及其子目录下所有文件
```

3. chmod: 修改文件权限

```shell
chmod ugo+rwx file.txt
# 将文件设定为所有人均可读写执行
# u--拥有者; g--组; o--其它用户; r--读; w--写; x--执行
# ---- --- ---
```

4. 常用命令

```shell
# 添加用户到组
gpasswd -a USER_NAME GROUP_NAME

```

5. 远程传输

```shell
# 本机文件/文件夹拷贝到远程主机
scp -P 10022 -r [folderPath] [remoteUser]@[remoteIp]:[remotePath]
# 从远程主机拷贝文件
scp -P 10022 -r [remoteUser]@[remoteIp]:[remotePath] [folderPath]
# 选项 -C 可以启用ssh压缩功能, 传输速度更快
```

6. 远程登录

```shell
ssh [remoteUser]@[remoteIp]
```





   

   

