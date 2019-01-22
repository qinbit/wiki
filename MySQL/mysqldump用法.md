# 语法格式
mysqldump [options] db_name [tbl_name ...]        备份指定库的多张表   
mysqldump [options] --databases db_name ...       备份多个库
mysqldump [options] --all-databases               备份所有库

# 重要参数说明
| options     | Description |
| ----------- | ----------- |
|--quick      |若不开启，备份数据将先缓存到内存中，大表备份时须开启，防止内存空间不够导致备份失败。--opt选项（默认开启）附带开启--quick选项|
|--add-locks   |在insert语句前加锁，若目标数据库已经投产，则评估影响情况。使用--skip-add-locks关闭|
|--comments    |在备份文件中添加额外信息。无用干扰信息，默认开启，使用 --skip-comments关闭|
|-c           |insert语句中使用完整的列名|
|-a，--create-options|    包含create语句，-opt选项（默认开启）附带开启--create-options选项，使用--skip-create-options关闭|
|--default-character-set|  默认字符集，默认utf8|
|--disable-keys |在insert语句前设置设置所有索引约束无效，若目标数据库已经投产，则使用--skip-disable-keys关闭|
|--dump-date    |当--comments选项开启后，将备份日期注释到备份文件，无用干扰信息，默认开启，使用--skip-dump-date关闭|
|--extended-insert|    使用 multiple-row INSERT语法，默认开启，使用 --skip-extended-insert 关闭|
|-f, --force    |SQL有误，强制继续执行，默认FALSE|
|--insert-ignore  |使用 INSERT IGNORE 语法进行插入，默认关闭|
|--max-allowed-packet|   最大发送或接受到MySQL服务的包，该值应当小于目标数据库的参数值|
|--net-buffer-length  |  Buffer size for TCP/IP and socket communication，multiple-row INSERT 的行数等于该值|
|-n, --no-create-d     | 不写 CREATE DATABASE 语句|
|-t, --no-create-info  |  不写 CREATE TABLE 语句|
|-opt    |选项简写，默认开启，包括：--add-drop-table --add-locks --create-options --disable-keys --extended-insert --lock-tables --quick --set-charset|
|--replace  | 使用 REPLACE 代替 INSERT 语法，增量备份使用|
|--single-transaction  |  备份前开启事务|
|--tz-utc  |  备份前设置时区，以保证数据迁移不受时区影响|
|--where    | 添加过滤条件|
