### BeautifulSoup的使用
http://cuiqingcai.com/1319.html
#### 开始使用
```python
soup = BeautifulSoup(html, "html.parser")
#lxml解析html更好一些，默认的html.parser容易出现错误
soup = BeautifulSoup(html, "lxml")
```

#### 选择器
```python
#返回的是字符串列表
print soup.select("div[id='shop-all-list']")[0]
```

#### find查找
```python
# 查找class为sister的所有标签对象
soup.find_all("a", class_="sister")
# 查找某一属性值
print baseinfo.find("span", itemprop="street-address")
#查找div的class为多个值的div
print baseinfo.find("div", class_=["other", "J-other"])
#获取标签的属性
print tagObj.attrs("class")
# 非递归查找，获取所有直接子孙节点
print tagObj.find_all("li", recursive=False)
```

#### find_next, 查找元素的下一个元素
```python
print tagObj.find_next("a")
```

#### children子元素获取
```python
#返回子元素的列表
tagObj.findChildren()
```

#### 获取标签的内容
```python
# 返回包含原始数据的列表
tagObj.contents
# 返回去除html标签的文本数据
tagObj.text
```
