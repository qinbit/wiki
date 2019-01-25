# 文件下载服务
```
location / {
    alias /export/share/test/; 	# 文件存放目录，注意要以 '/' 结尾；
    index index.html;  		    # 如果文件存放目录有 index.html，会跳转到 index.html；
    autoindex on;               # 自动列出目录下的文件；
    autoindex_exact_size off;   # 文件大小按 G、M 的格式显示，而不是 Bytes；
}
```
