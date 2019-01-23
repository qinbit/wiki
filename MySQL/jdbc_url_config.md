|参数名称	|参数说明	|缺省值|	最低版本要求|
| ----------- | ----------- | ----------- | ----------- |
|user	|数据库用户名（用于连接数据库）|	|所有版本|
|password	|用户密码（用于连接数据库）	| |所有版本|
|useUnicode	|是否使用Unicode字符集，如果参数characterEncoding设置为gb2312或gbk，本参数值必须设置为true	|false	|1.1g|
|characterEncoding	|当useUnicode设置为true时，指定字符编码。比如可设置为gb2312或gbk	|false	|1.1g|
|autoReconnect	|当数据库连接异常中断时，是否自动重新连接	|false	|1.1|
|autoReconnectForPools	|是否使用针对数据库连接池的重连策略	|false	|3.1.3|
|failOverReadOnly	|自动重连成功后，连接是否设置为只读	|true	|3.0.12|
|maxReconnects	|autoReconnect设置为true时，重试连接的次数	|3	|1.1|
|initialTimeout	|autoReconnect设置为true时，两次重连之间的时间间隔，单位：秒	|2	|1.1|
|connectTimeout	|和数据库服务器建立socket连接时的超时，单位：毫秒。 0表示永不超时，适用于JDK 1.4及更高版本|	0	|3.0.1|
|socketTimeout	|socket操作（读写）超时，单位：毫秒。 0表示永不超时	|0	|3.0.1|
