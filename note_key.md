## Redis keys 命令
| 命令 | 描述 |
|------|------|
| DEL key | key存在的时候删除key |
| DUMP key | 序列化指定key,并返回被序列化的值 |
| EXISTS key | 检查key是否存在 |
| EXPIRE key | 设置key的过期时间，key过期后将不再可用，单位以秒计 |
| EXPIREAT key | 设置key的过期时间， 接收的参数是UNIX时间出(unix timestamp)|
| PEXPIRE key | 设置key的过期时间，单位以毫秒计 |
| PEXPIREAT key | 设置key的过期时间，接收的参数是UNIX时间，以毫秒计 |
| KEYS pattern | 查找符合条件的所有key |
| MOVE key db | 将当前key移动到指定数据库中 |
| PERSIST key | 移除给定key的过期时间，使key永不过期 |
| PTTL key | 以毫秒没为单位返回指定key的剩余过期时间 |
| TTL key | 以秒为单位，返回指定key的剩余过期时间 |
| RANDOMKEY | 随机返回一个key |
| RENAME key new_key | 修改key的名称 |
| RENAMENX key new_key | 仅当new_key不存在时，将key修改为new_key |
| TYPE key | 返回key存储的数据类型 |

## 字符串
| 命令 | 描述 |
|------|------|
| SET key value | 设置指定key的值 |
| GET key | 获取指定key的值 |
| GETRANGE key start end | 返回key中字符串值的子字符串 |
| GETSET key value | 将给定的key的值设置为value, 并返回旧值 old value |
| GETBIT key offset | 对key所春初的字符串值，获取指定偏移量上的位(bit) |
| MGET key | 获取所有(一个或多个)给定key的值 |
| SETNX key value | 只有在key不存在的时候设置key的值为value |
| SETBIT key offset value | 对指定key的字符串设置或删除指定偏移量上的位 |
| SETEX key seconds value | 将key关联到value并将key的过期时间设为seconds(以秒为单位) |
| SETRANGE key offset value | 用value参数覆盖key所存储的字符串值，从偏移量offset开始 |
| MSETNX key value [key value...] | 同时设置多个key-value,只支持所有的key都不存在的情况 |
| PSETEX key milliseconds vale | 与SETEX类似，过期时间为毫秒 |
| INCR key | 将key中存储的数值增1 |
| INCRBY key value | 将key所存储的值增加指定value |
| INCRBYFLOAT key value | 将key所存储的值增加浮点增量值value |
| DECR key | 将key中存储的值减去1 |
| DECRBY key value | 将key中存储的值减去指定的value |
| APPEND key vale | 如果key已经存在并且是一个字符串，APPEND命令将指定的value追加到原来value的末尾 |


`KEYS runoob*` 查找以runoob开头的key
