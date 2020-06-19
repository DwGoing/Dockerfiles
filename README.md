# Dockerfiles

常用的Docker File，使用以下命令构建镜像。

```shell
docker build -t <镜像名称> https://raw.githubusercontent.com/Dwgoing/Dockerfiles/master/<文件夹>/Dockerfile
```

1. CentOS-SSH

   已开启SSH服务的CentOS镜像，使用以下命令运行并修改root密码。

   ```shell
   docker run -itd <镜像名称>
   docker exec -i <容器名称> passwd
   ```

