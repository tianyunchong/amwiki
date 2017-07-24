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
