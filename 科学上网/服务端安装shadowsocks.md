# CentOS7服务器安装 Shadowsocks

1. 安装epel-release  
    wget http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm  
    rpm -Uvh epel-release-latest-7.noarch.rpm  
2. 安装pip工具  
    yum install python python-pip  
3. 安装shadowsocks  
    pip install shadowsocks  
4. 在/etc/shadowsocks/config.json文件编辑如下内容    
    {  
        "server":"0.0.0.0",  
        "server_port":666,  
        "local_port":1080,  
        "password":"password",  
        "timeout":600,  
        "method":"aes-256-cfb",  
        "fast_open":false  
    }
5. 启动服务
    ssserver -c /etc/shadowsocks/config.json -d start (stop 停止；restart 重启)  
