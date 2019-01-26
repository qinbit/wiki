# 静待IP绑定

编辑文件 /etc/sysconfig/network-script/ifcfg-enoxxxx
```
#BOOTPROTO="dhcp"
#DEFROUTE="yes"
#IPV4_FAILURE_FATAL="no"
#IPV6INIT="yes"
#IPV6_AUTOCONF="yes"
#IPV6_DEFROUTE="yes"
#IPV6_FAILURE_FATAL="no"
#IPV6_ADDR_GEN_MODE="stable-privacy"
BOOTPROTO="static"
MM_CONTROLLED="yes"
IPADDR="192.168.168.3"
NETMASK="255.255.255.0"
GATEWAY="192.168.168.2"
DNS1="114.114.114.114"
DNS2="114.114.115.115"
```

重启网卡
```

```
