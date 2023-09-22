1. redis客户端连接服务端

   redis-cli -h ${ip} -p ${port} -a {password} 

2. 关闭redis服务端

   redis-cli -h ${ip} -p ${port} -a {password} shutdown

3. redis.conf

   1. daemonize yes -- 以守护进程启动, 

   2. pidfile path 守护进程启动时, 启动后redis会默认把pid写入到/var/run/redis.pid文件中, 可以通过pidfile /var/run/redis/pid来指定

   3. save 指定多长时间  多少次更新, 后做持久化

      save 900 10  900秒内有10次更新则持久化

   4. rbdcompression yes 持久化时, 是否采用压缩算法LZF, no以节约cpu

   5. dbfilename dump.rdb 持久化的文件名本地命名

   6. dir ./ 指定持久化本地数据存放目录

   7. requirepass pass  设置连接密码

   8. maxmemory <bytes> 指定redis最大内存限制

4. redis内存维护策略

   1. 设置key过期时间 -- expire ${key} ${time, seconds}

   2. 采用LRU算法动态将不用的数据删除

      > 内存中存在但是不使用的数据块(内存块)叫做LRU

      1. 策略: volatile-lru; allkeys-lru 所有key中最不常用的数据进行删除
   
5. redis数据类型

   > string, hash, list, set及zset(sorted)等

6. 常用命令

   keys *:  返回所有的key

   exists key: 判断是否存在key -> 1: 存在; 0: 不存在

   expire key second: 设置key的过期时间;

   ttl key: 查看key剩余多少时间过期; key不存在返回-2, 存在无过期时间返回-1;

   persist key: 取消key的过期时间

   del keys: 删除keys

   rename key key: key重命名

   pexpire key milliseconds: 修改过期时间单位为毫秒

   select 0-15; 选择一个数据库;

   move key dbindex: 将key移动到指定数据库

   dbsize: 查看数据库key的数量;

   flushdb: 清空当前数据库  flushall: 清空所有

   randomkey: 随机返回一个key

   type key: 返回key的数据类型

   

7. string类型常用命令

   GETRANGE key start end : 截取指定key的字符串

   GETSET key value: 用于设定指定key的值, 并返回旧值, 当key不存在时返回nil

   STRLEN key: 返回key所存储字符串的长度

   incr: 自增 decr: 自减  incrby, decrby(数字类型字符串)

   APPEND key value: 拼接字符串

8. 

   

   

   

   

   

