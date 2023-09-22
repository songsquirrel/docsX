## Appenders

[logback中文文档](http://www.logback.cn/)

1. ConsoleAppender

```xml
<configuration>

    <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender" >
        <!-- encoder 默认使用 ch.qos.logback.classic.encoder.PatternLayoutEncoder -->
        <encoder>
            <pattern>%-4relative [%thread] %-5level %logger{35} - %msg %n</pattern>
        </encoder>    
    </appender>

    <root level="DEBUG">
        <appender-ref ref="STDOUT" />
    </root>
</configuration>
```

2. SocketAppender and SSLSocketAppender

    > 将日志输出到远程服务器



