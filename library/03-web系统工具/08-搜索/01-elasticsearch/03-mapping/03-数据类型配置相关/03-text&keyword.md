#### text和keyword类型
https://my.oschina.net/jsonyang/blog/1204659
5.*之后，把string字段设置为了过时字段，引入text，keyword字段
这两个字段都可以存储字符串使用，但建立索引和搜索的时候是不太一样的

keyword：存储数据时候，不会分词建立索引
text：存储数据时候，会自动分词，并生成索引（这是很智能的，但在有些字段里面是没用的，所以对于有些字段使用text则浪费了空间）。
