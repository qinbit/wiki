# JVM常用参数

| 参数 | 说明 | 收集器 | jdk版本 |
| ---- | ---- | ---- | ---- |
| -Xmn | 年轻代大小（eden+ 2 survivor space），Sun官方推荐配置为整个堆的3/8 | | |
| -Xms | 设置初始的堆大小 | | |
| -Xmx | 设置最大的内存分配大小，一般的服务端部署，-Xms和-Xmx设置为同样大小 | | |
| -Xss | 设置thread stack大小，Linux/x64 (64-bit): 1024 KB | | |
| -XX:+HeapDumpOnOutOfMemoryError | 当JVM发生OOM时，自动生成DUMP文件 | | |
| -XX:HeapDumpPath=${目录} | 表示生成DUMP文件的路径，也可以指定文件名称 | | |
| -Dproperty=value | 设置系统属性，设置后的属性可以在代码中System.getProperty方法获取到 | | |
| -verbose:class | 展示的每个class的信息 | | |
| -verbose:gc | 展示每个GC事件的信息 | | |
| -verbose:jni | 展示JNI调用信息 | | |
| -XX:MaxDirectMemorySize=size | 为NIO的direct-buffer分配时指定最大的内存大小。| | |
| -XX:MetaspaceSize | 初始空间大小 | | |
| -XX:MaxMetaspaceSize | 最大空间，默认是没有限制的。 经测试该参数没有生效 | | |

