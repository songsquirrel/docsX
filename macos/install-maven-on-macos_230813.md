## install maven on macos

    在 macos 上安装 Maven，因为 Maven 运行需要依赖 Java，所以需先安装 Java。

1. 安装 Java，配置环境变量

    openJDK 下载地址：https://jdk.java.net/20

    压缩包解压命令：

    ```shell
    # 解压下载后安装包
    tar -xvf openjdk-20.0.1_osx-Aach_bin.tar.gz
    # 移动包至安装目录
    sudo mv jdk-20.0.1.jdk /Library/Java/JavaVirtualMachines/
    ```
2. 设置 Java环境变量

    使用～/.bash_profile 或 ～/.zshrc配置。完成使用 source 使配置生效，使用 java -version 验证是否成功。

    ```shell
    JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk-13.0.1.jdk/Contents/Home"
    PATH="${JAVA_HOME}/bin:${PATH}"
    export PATH
    ```
3. 安装 Maven
   
   [下载地址](https://maven.apache.org/download.cgi)
4. 解压并移动至安装目录，配置环境变量（同 java）
5. 使用 mvn -version 验证是否配置成功


[参考资料](https://www.digitalocean.com/community/tutorials/install-maven-mac-os#install-maven-on-mac)