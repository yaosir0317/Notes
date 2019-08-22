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

# PostGIS插件

PostGIS是对象关系型数据库PostgreSQL的一个插件，PostGIS提供如下空间信息服务功能：空间对象、空间索引、空间操作函数和空间操作符, 包括：点（POINT）、线（LINESTRING）、多边形（POLYGON）、多点 （MULTIPOINT）、多线（MULTILINESTRING）、多边形（MULTIPOLYGON）和集合对象集 （GEOMETRYCOLLECTION）等。同时，PostGIS遵循OpenGIS的规范。

- 安装

  ```
  yum install postgis2_96   # 因为安装的PostgreSQL版本为9.6，所以是postgis2_96
  ```

- 为数据库安装

  ```
  gisdb=# CREATE EXTENSION postgis;
  gisdb=# CREATE EXTENSION postgis_topology;
  ```

- 检查

  ```
  \dx  # 查看是否安装成功插件
  ```

  