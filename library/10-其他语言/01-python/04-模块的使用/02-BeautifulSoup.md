### BeautifulSoup的使用
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
