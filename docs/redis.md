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

- KEYS pattern

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