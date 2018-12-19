将tomcat8用户设置为nologin
usermod -s /sbin/nologin tomcat8

切换至nologin用户
su - tomcat8 --shell=/bin/bash

将tomcat8用户取消nologin设置
usermod -s /bin/bash tomcat8
