# 修改国内yum源
yum install -y yum-utils
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo


# 修改国内镜像
1. /etc/docker/daemon.json 中写入如下内容（如果文件不存在请新建该文件）
```
{
  "registry-mirrors": [
    "https://registry.docker-cn.com",
    "http://hub-mirror.c.163.com"
  ]
}
```

2. 重新启动服务
```
systemctl daemon-reload
systemctl restart docker
```
