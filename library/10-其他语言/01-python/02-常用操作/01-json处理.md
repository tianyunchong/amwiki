## python中json字符串的处理
```python
import json
```
> 编码：把一个Python对象编码转换成Json字符串   json.dumps()

> 解码：把Json格式字符串解码转换成Python对象   json.loads()

### 使用案例
#### 排序
```python
# 将字段转成json字符串,并排序
data1 = {'b':789,'c':456,'a':123}
d1 = json.dumps(data1,sort_keys=True)
```

#### 缩进
```python
# 转成json字符串的同时，并对字符串内容缩进
data1 = {'b':789,'c':456,'a':123}
d1 = json.dumps(data1,sort_keys=True,indent=4)
print d1
```


#### 压缩
```python
data1 = {'b':789,'c':456,'a':123}
b = json.dumps(data1, separators=(',', ":"))
print len(repr(b))
```
