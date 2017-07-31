### model类使用查询
```php
# 查询一条数据
$model = Pdinfo::findFirst(array(
  "conditions" => "pid = ?1 and state = 1",
  "bind"       => array(1 => 1000),
  "limit"      => 1,
));
```
