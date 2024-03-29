准备SQL执行文件export.sql：
```
set colsep  ,
set feedback off
set heading off
set newp none
set pagesize 0
set linesize 200
set trimout on

spool /data/export.csv

select t.name||','||t.age||','||t.salary||','||t.email||','||t.title
from employee t
where t.age < 50
order by t.salary desc;  

spool off  
exit
```

说明：
```
set colsep  , #分割符
set feedback off #回显本次sql命令处理记录条数
set heading off # 输出标题
set newp none #设置查询出来的数据分多少页显示，如果需要连续的数据，中间不要出现空行就把newp设置为none
set pagesize 0 # 输出每页行数，为了避免分页设置为0
set linesize 200 # 每行大小，如果设置太小，会分行，最好是超好输出最大值
set trimout on # 去除标准输出每行的拖尾空格
set termout off #显示脚本中的命令的执行结果
set echo on #设置运行命令是否显示语句
set numwidth 12 # 输出number类型域长度
```

执行：
```
sqlplus user/pass@db @export.sql
```

可以通过SQL指定文件名：
```
col datestr new_value filename
select '/data/export.'||to_char(sysdate,'yyyymmdd')||'.csv' datestr from dual;
spool &filename
```

from https://segmentfault.com/a/1190000022679279
