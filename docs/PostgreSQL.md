# 常用数值类型

#### 数值型

- integer(int)
- real(浮点)
- serial(序列)

#### 文字型

- char
- varchar
- text

#### 布尔型

- boolean

#### 日期型

- date
- time
- timestamp

#### 特色类型

- Array
- 网络地址型(inet)
- JSON
- XML

# 方便的函数

- `length`计算字符串长度

- `concat`连接字符串

  ```
  select name, concat(age, '--', address) from users;
  ```

- `alias`将字段赋予别名展示

  ```
  select name, concat(age, '--', address) as "拼接字符串" from users;
  ```

- `substring`切割字符串

  ```
  select substring(name,1,2) from users;  /* 从第一字符开始切2个
  ```

- `random`随机数

  ```
  select * from users order by random() limit 1;
  ```

  