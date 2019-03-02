# JVM常用参数

| 参数 | 说明 |
| ---- | ---- |
| -Xms | 设置初始的堆大小 |
| -Xmx | 设置最大的内存分配大小，一般的服务端部署，-Xms和-Xmx设置为同样大小 |
| -XX:+HeapDumpOnOutOfMemoryError |  |
| -Dproperty=value | 设置系统属性，设置后的属性可以在代码中System.getProperty方法获取到 |
| -verbose:class | 展示的每个class的信息 |
| -verbose:gc | 展示每个GC事件的信息 |
| -verbose:jni | 展示JNI调用信息 |
