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
| -Xloggc:/appl/gclogs/gc.log | | | |
| -verbose:gc | 展示每个GC事件的信息 | | |
| -XX:+PrintGcDetails | 发生垃圾收集行为时，打印日志 | | |
| -XX:+PrintGCTimeStamps | | | |
| -XX:+PrintGCDateStamps | | | |
| -verbose:jni | 展示JNI调用信息 | | |
| -XX:MaxDirectMemorySize | 为NIO的direct-buffer分配时指定最大的内存大小。| | |
| -XX:MetaspaceSize | 初始空间大小 | | |
| -XX:MaxMetaspaceSize | 最大空间，默认是没有限制的。 经测试该参数没有生效 | | |
| -XX:SurvivorRatio | 新生代Eden区与Survivor区的空间比例，默认为8，代表 Eden:Survivor=8:1 | | |
| -XX:NewRatio | new/old 年代的大小比例，默认值 2 | | |
| -XX:MaxTenuringThreshold | 对象晋升年代的最大阀值，默认值 15（最大值） |
| -XX:PretenureSizeThreshold | 直接晋升老年代的对象大小 |
| -XX:+UseSerialGC | 使用Serial+Serial Old收集器组合 | Serial+Serial Old | |
| -XX:+UseParNewGC | 使用ParNew+Serial Old收集器组合 | ParNew+Serial Old | |
| -XX:+UseConcMarkSweepGC | 使用ParNew+CMS+Serial Old收集器组合 | ParNew+CMS+Serial Old | 1.5 |
| -XX:+UseParallelGC | 使用Parallel+Serial Old收集器组合 | Parallel+Serial Old | 1.4 |
| -XX:+UseParallelOldGC | 使用Parallel+Parallel Old收集器组合 | Parallel+Parallel Old | 1.6 |
| -XX:+UseG1GC | 使用 Garbage First (G1) 收集器 | G1/Parallel | |
| -XX:MaxGCPauseMillis | 设置最大GC 暂停时间 | G1/Parallel | |
| -XX:+UseAdaptiveSizePolicy | 动态调整Java堆中各区域大小以及进入老年代的年龄 | Parallel |
| -XX:GCTimeRatio | GC时间占总时间的比率，默认99，即允许1%的GC时间 | Parallel |


