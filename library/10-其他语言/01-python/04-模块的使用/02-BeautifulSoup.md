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
#获取标签的属性
print tagObj.attrs("class")
```


#### children子元素获取
```python
#返回子元素的列表
tagObj.findChildren()
```
