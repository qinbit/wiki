将tomcat8用户设置为nologin

```shell
usermod -s /sbin/nologin tomcat8
```

切换至nologin用户

```shell
su - tomcat8 --shell=/bin/bash
```

将tomcat8用户取消nologin设置

```shell
usermod -s /bin/bash tomcat8
```
