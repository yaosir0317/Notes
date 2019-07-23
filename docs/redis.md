# 命令

## keys

- `DEL key [key...]` 

  > **Time complexity:** O(1)

  删除一个或多个key,如果不存在则被忽略;返回删除个数

- `EXISTS key [key...]`

  > **Time complexity:** O(1)

  判断一个或多个key是否存在 ,返回存在的数量

- `EXPIRE key seconds`

  > **Time complexity:** O(1)

  为key设置过期时间单位为秒,成功返回1,key不存在返回0

- `EXPIREAT key timestamp`

  > **Time complexity:** O(1)

  为key设置过期时间,以Unix时间戳为依据,成功返回1,key不存在返回0

- `KEYS pattern`

  > **Time complexity:** O(n)

  返回pattern匹配到的所有key

  ```
  h?llo matches hello, hallo and hxllo
  h*llo matches hllo and heeeello
  h[ae]llo matches hello and hallo, but not hillo
  h[^e]llo matches hallo, hbllo, ... but not hello
  h[a-b]llo matches hallo and hbllo
  ```

- `PERSIST key`

  > **Time complexity:** O(1)

  清除过期时间,成功返回1,key不存在或没有为持久key则返回0

- `PEXPIRE key milliseconds`

  > **Time complexity:** O(1)

  设置过期时间,单位为毫秒

- `PEXPIREAT key milliseconds-timestamp`

  > **Time complexity:** O(1)

  与EXPIREAT类似,同样是毫秒为单位

- `TTL key`

  > **Time complexity:** O(1)

  返回key剩余的过期时间,以秒为单位

- `PTTL key`

  > **Time complexity:** O(1)

  返回剩余的过期时间,以毫秒为单位

- `RANDOMKEY`

  > **Time complexity:** O(1)

  返回当前库中的随机一个key

- `RANAME key newkey`

  > **Time complexity:** O(1)

  将key重新命名为newkey,当key不存在时报错,当newkey存在时,key值将被覆盖

- `RANAMENX key newkey`

  > **Time complexity:** O(1)

  将key重新命名为newkey,当newkey不存在时创建,当newkey存在时,newkey值将被覆盖

- `SCAN cursor`

  > **Time complexity:** O(1)

  扫描key,他有两个返回值,第一个位下次扫描所使用的的cursor,第二个位扫描出的键值

  ```
  SCAN iterates the set of keys in the currently selected Redis database.
  SSCAN iterates elements of Sets types.
  HSCAN iterates fields of Hash types and their associated values.
  ZSCAN iterates elements of Sorted Set types and their associated scores
  ```

- `TOUCH key [key...]`

  > **Time complexity:** O(N) where N is the number of keys that will be touched.

  更新key的最新访问时间

- `TYPE key`

  > **Time complexity:** O(1) 

  返回key对应值得类型

- `UNLINK key [key...]`

  > **Time complexity:** O(1) 

  删除key,与del不同的是它不会造成阻塞

## string

- `APPEND key value`

  > **Time complexity:** O(1)

  如果key存在,且值为字符串,这个命令会向字符串末尾添加value,如果key不存在,将会创建

- `BITCOUNT key [start end]`

  > **Time complexity:** O(N)

  返回字符串的bit数目

- `DECR key`

  > **Time complexity:** O(1)

  将键对应的int值减一,如果key不存在,则创建使其值为0,再进行操作;如果键对应的值不能转换为int则会报错

- `DECRBY key decrement`

  > **Time complexity:** O(1)

  将键对应的int值减decrement数量,如果key不存在,则创建使其值为0,再进行操作;如果键对应的值不能转换为int则会报错

- `GET key`

  > **Time complexity:** O(1)

  返回key对应的字符串值,当值不是字符串类型,则会报错,因为get只用于获取字符串值,当key不存在返回nil

- `GETRANGE key start end`

  > **Time complexity:** O(N)

  以切片形式获取key对应的字符串的值,支持从右向左取,也就是负索引

- `GETSET key value`

  > **Time complexity:** O(1)

  将value值赋值给key,返回key的原始值,非字符串会报错

- `INCR key`

  > **Time complexity:** O(1)

  将键对应的int值加一,如果key不存在,则创建使其值为0,再进行操作;如果键对应的值不能转换为int则会报错

- `INCRBY key increment`

  > **Time complexity:** O(1)

  将键对应的int值加上increment数量,如果key不存在,则创建使其值为0,再进行操作;如果键对应的值不能转换为int则会报错

- `INCRBYFLOAT key increment`

  > **Time complexity:** O(1)

  将键对应的int值加上increment的浮点数量,如果key不存在,则创建使其值为0,再进行操作;如果键对应的值不能转换为int则会报错

- `MGET key [key ...]`

  > **Time complexity:** O(N) where N is the number of keys to retrieve

  返回给出key的值,当key不存在或非字符串则返回nil

- `MSET key value [key value...]`

  > **Time complexity:** O(N) where N is the number of keys to set.

  写入给出的键值,当前操作会覆盖已有的键的值

- `MSETNX key value [key value...]`

  > **Time complexity:** O(N) where N is the number of keys to set.

  写入给出的键值,当写入的键值已存在时,将不会写入,且操作为原子性

- `PSETEX key milliseconds value`

  > **Time complexity:** O(1)

  设置键值时同时设置上过期时间,单位为毫秒

- `SET key value[expiration EX seconds|PX milliseconds] [NX|XX]`

  > **Time complexity:** O(1)

  设置键值,会覆盖已有的,并且有一些额外的选项可以使用

  ```
  EX seconds -- Set the specified expire time, in seconds.
  PX milliseconds -- Set the specified expire time, in milliseconds.
  NX -- Only set the key if it does not already exist.
  XX -- Only set the key if it already exist.
  ```

- `SETEX key seconds value`

  > **Time complexity:** O(1)

  设置键值时同时设置上过期时间,单位为秒

- `SETNX key value`

  > **Time complexity:** O(1)

  当键值不存在时,设置键值

- `SETRANGE key offset value`

  > **Time complexity:** O(1)

  覆盖偏移量后面部分的字符串的值

- `STRLEN key`

  > **Time complexity:** O(1)

  返回key所对应的字符串的长度