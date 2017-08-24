#### mapping修改
如果想修改mapping中一个字段的类型或者分词器，提交会失败，这是因为该字段的所有数据都要重新索引，所以是不允许修改的，如果要修改，只能创建个新的索引，然后使用alias，实现新的索引
```shell
//给现有的索引增加别名指向
```


#### mapping映射创建
```shell
curl -XPOST "http://localhost:9200/test_index/products/_mapping" -d '
{
	"products" : {
		"properties" : {
			"title": {"type" : "text", "analyzer" : "ik_max_word"}
		}
	}
}
'
```
