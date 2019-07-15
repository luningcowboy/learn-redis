## 安装
1. 从`http://download.redis.io/redis-stable.tar.gz`下载
2. 解压`tar xzf redis-stable.tar.gz`
3. 安装`cd redis-stable.tar.gz | make`
4. 安装到`/usr/local/bin` ==>`make install`
### 注意
1. 测试`make test`
## 启动和停止
最常用的两个程序`redis-server`和`redis-cli`
`redis-server`是Redis的服务器，启动Redis即运行`redis-server`
`redis-cli`是Redis自带的Redis命令行客户端
### 启动
直接运行`redis-server`
Redis默认端口6379,可以通过`--port`指定端口号,例如:`redis-server --port 6380`
### 停止Redis
运行命令`redis-cli SHUTDOWN`
Redis可以妥善处理SIGTERM信号，所以直接使用`kill redis进程的PID`也可以正常结束Redis,效果与使用`SHUTDOWN`命令一样。

## 发送命令
1. 连接redis: `redis-cli -h 120.0.0.1 -p 6379` 或者 `redis-cli`
2. 测试是否连通: `PING` 如果返回`PONG` 说明连接成功
## 命令返回值
### 五种返回状态
1. 状态回复: `PING` 回复 `PONG`
2. 错误回复: `TEST_CMD` 回复
```
(error) ERR unknown command `TESTCMD`, with args beginning with
```
3. 整数回复: `INCR foo`
```
(integer) 1
```
4. 字符串回复: 
```
GET foo
2"
GET noexites
(nil)
```
5. 多行字符串回复:
```
KEYS *
1) "foo"
```
__KEYS命令的作用是获取数据库中符号指定规则的键名__
## 配置
1. 配置模块源码下redis.conf
2. 在不重启redis的情况下修改配置:`CONFIG SET loglevel warning`
3. 获取redis当前的配置:`CONFIG GET loglevel`
4. 使用配置启动redis `redis-server confi_path`

## 多数据库
redis默认支持16个数据库，可以通过配置参数database来修改这一数字，客户端跟redis建立连接的时候会自动选择0号数据库，不过可以通过SELECT
命令更换数据库.
```
SELECT 1
OK
```
## 获得符合规则的键名
`KEYS pattern`









[redis下载路径](http://download.redis.io/redis-stable.tar.gz)
