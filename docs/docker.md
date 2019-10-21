# 守护式容器

## 方式一

```
docker run -it --name centos /bin/bash  # 以交互式启动容器
# ctrl+p  ctrl+q 退出后,容器就变为守护式来
# 通过docker attach centos 可以重新进入交互式
```

## 方式二

```
docker run --name centos -d centos /bin/bash  # 以守护式启动容器
```

## exec

在运行中的容器中启动新进程

```
docker exec -it centos /bin/bash
```

## 停止容器

- docker stop 给容器发出信号,等待其结束
- docker kill  直接停止容器

# 构建镜像

## 使用commit构建

## 使用Dockerfile构建

### 指令

- FROM

  > 指定基础镜像,必须是第一行非注释指令

- MAINTAINER

  > 指定镜像的作者信息

- RUN

  > 指定镜像中运行的指令

  - shell模式
  - exec模式

- EXPOSE

  > 指定一个或多个端口
  >
  > 但是同样需要在RUN命令需要指定端口的映射

- CMD

  > 指定容器运行中的默认命令, run指定会将其覆盖

  - exec
  - shell
  - ENTRYPOINT

- ENTRYPOINT

  > 与CMD类似但是不会被RUN指定的命令覆盖, 如果想覆盖需要添加指令

- ADD

  > 将文件或目录复制到Dockerfile创建的镜像中
  >
  > 包含类似的解压功能

- COPY

  > 将文件或目录复制到Dockerfile创建的镜像中
  >
  > 单纯的复制文件

- VOLUME

  > 

- WORKDIR

  > 在容器内部创建工作目录, 绝对目录

- ENV

  > 设置环境变量

- USER

  > 指定运行镜像的用户身份

- ONBUILD

  > 为镜像添加触发器,当被用于子镜像时,将会触发

