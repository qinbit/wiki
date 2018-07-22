# MySQL代理配置
```
#---------------------------------------------------------------------
# Global settings
#---------------------------------------------------------------------
global
    # to have these messages end up in /var/log/haproxy.log you will
    # need to:
    #
    # 1) configure syslog to accept network log events.  This is done
    #    by adding the '-r' option to the SYSLOGD_OPTIONS in
    #    /etc/sysconfig/syslog
    #
    # 2) configure local2 events to go to the /var/log/haproxy.log
    #   file. A line like the following can be added to
    #   /etc/sysconfig/syslog
    #
    #    local2.*                       /var/log/haproxy.log
    #
    log         127.0.0.1 local2

    chroot      /var/lib/haproxy
    pidfile     /var/run/haproxy.pid
    maxconn     4000
    user        haproxy
    group       haproxy
    daemon

    # turn on stats unix socket
    stats socket /var/lib/haproxy/stats

#---------------------------------------------------------------------
# common defaults that all the 'listen' and 'backend' sections will
# use if not designated in their block
#---------------------------------------------------------------------
defaults
        log global
        option dontlognull
        retries 3
        timeout queue 1m
        timeout connect 10s
        timeout client 1m
        timeout server 1m
        timeout check 10s
        maxconn 600

# MySQL代理
frontend mysql
        bind *:3307
        mode tcp
        log global
        default_backend mysqlservers

# Mysql真正服务
backend mysqlservers
        balance leastconn
        server dbsrv1 192.168.197.102:3306 check port 3306 rise 1 fall 2 maxconn 300
        server dbsrv2 192.168.197.103:3306 check port 3306 rise 1 fall 2 maxconn 300 backup

# Haproxy统计页
listen stats
        mode http
        bind 0.0.0.0:1080
        stats enable
        stats hide-version
        stats uri /haproxyadmin?stats
        stats realm Haproxy\ Statistics
        stats auth admin:admin
        stats admin if TRUE
```