# Druid连接池常用配置

参数 | 说明
--- | ---
testWhileIdle | 建议配置为true，不影响性能，并且保证安全性。申请连接的时候检测，如果空闲时间大于timeBetweenEvictionRunsMillis，执行validationQuery检测连接是否有效。
testOnBorrow | 申请连接时执行validationQuery检测连接是否有效，做了这个配置会降低性能。
testOnReturn | 归还连接时执行validationQuery检测连接是否有效，做了这个配置会降低性能。
timeBetweenEvictionRunsMillis | 1) Destroy线程会检测连接的间隔时间，如果连接空闲时间大于等于minEvictableIdleTimeMillis则关闭物理连接。2) testWhileIdle的判断依据，详细看testWhileIdle属性的说明
minEvictableIdleTimeMillis | 连接保持空闲而不被驱逐的最小时间
maxWait | 获取连接时最大等待时间，单位毫秒。配置了maxWait之后，缺省启用公平锁，并发效率会有所下降，如果需要可以通过配置useUnfairLock属性为true使用非公平锁。
useUnfairLock | 使用非公平锁
asyncInit | 如果有initialSize数量较多时，打开会加快应用启动时间
poolPreparedStatements | 是否缓存preparedStatement，也就是PSCache。PSCache对支持游标的数据库性能提升巨大，比如说oracle。在mysql下建议关闭。
maxPoolPreparedStatementPerConnectionSize | 要启用PSCache，必须配置大于0，当大于0时，poolPreparedStatements自动触发修改为true。
initialSize | 初始化时建立物理连接的个数。初始化发生在显示调用init方法，或者第一次getConnection时
web-stat-filter.enabled | 设为false可以关闭监控共呢个
