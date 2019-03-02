# zookeeper 常用命令

```
# 连接
./zkCli.sh -r -server 192.168.168.5:2181

# 断开
quit

# 查看某个节点下的所有子节点信息
ls path

# 获取指定节点的状态信息
stat path

# 获取节点的数据内容
get path
```
