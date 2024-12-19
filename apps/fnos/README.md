# 飞牛私有云 fnOS 的 Docker 移植测试

飞牛私有云fnOS 的docker移植测试，记得给权限并映射8000端口

## 命令行

```shell
docker run --name=fnOS --privileged -p 8088:8000 --detach=true -t makedie/fnos:0.8.13_test_202409140041
```

不给管理员就换SYS_ADMIN

```shell
docker run -d --name=fnOS --hostname=fnOS --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro --volume=/sys/fs/fuse:/sys/fs/fuse:rw --cap-add=SYS_ADMIN --cap-add=NET_ADMIN -p 8088:8000 --add-host fnOS:127.0.0.1 -t makedie/fnos:0.8.20_test
```

## 简单说明

把fnOS搬到docker上，方便大家截图玩
在/system完成设备初始化时会报错`Resource temporarily unavailable`或者是其他什么的 此时直接刷新页面正常登入就能进webui了
