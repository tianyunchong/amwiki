### requests
```shell
sudo pip install requests
```
#### 基本使用
```python
import requests
r = requests.get(url, headers=headers)
text = r.text.encode(r.encoding).decode("utf-8")
print text
```

#### 使用cookie
```python
# 第一步，请求首页或者一个页面，获取cookie信息
r = request.get(url_base)
cookies = r.cookies
# 第二部，请求页面，传递cookie
r = request.get(url, headers=headers, cookies=cookies)
# 其他，cookie的处理
# cookie转dict类型
cookies_dict = requests.utils.dict_from_cookiejar(r.cookies)
# dict类型cookie转cookiejar类型
cookies_jar = requests.utils.cookiejar_from_dict(cookies_dict)
```
