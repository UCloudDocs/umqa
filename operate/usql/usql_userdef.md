# 结合自定义字段查询

查询ping数据：

```sql
select
  definedata.key as definekey,
  definedata.val as definevalue,
  delay,
  loss
from(
  select definedata,delay,loss
  from ping,
  unnest(ping.user_defined) as t2(definedata) 
  where definedata.key = 'key1'
  and definedata.val = 'value1'
);
```

![](/images/operation_14.png)



查询tracert数据：

![](/images/operation_15.png)