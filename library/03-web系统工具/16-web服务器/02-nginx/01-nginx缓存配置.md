#### http协议的缓存配置
Cache-Control
> no-cache: 数据内容不能被缓存, 每次请求都重新访问服务器, 若有max-age, 则缓存期间不访问服务器.

> no-store: 不仅不能缓存, 连暂存也不可以(即: 临时文件夹中不能暂存该资源)

> private(默认): 只能在浏览器中缓存, 只有在第一次请求的时候才访问服务器, 若有max-age, 则缓存期间不访问服务器.

> public: 可以被任何缓存区缓存, 如: 浏览器、服务器、代理服务器等

> max-age: 相对过期时间, 即以秒为单位的缓存时间.

> no-cache, private: 打开新窗口时候重新访问服务器, 若设置max-age, 则缓存期间不访问服务器.

> private, 正数的max-age: 后退时候不会访问服务器

> no-cache, 正数的max-age: 后退时会访问服务器点击刷新: 无论如何都会访问服务器.

```shell
if ($request_uri ~* "^/$|^/search/.+/|^/company/.+/") {
    add_header    Cache-Control  max-age=3600;
}
location ~ .*\.(css|js|swf|php|htm|html )$ {
    add_header Cache-Control no-store;
}
location ~ .*\.(js|css)$ {
    expires 10d;
}
```

Expires
> 设置以分钟为单位的绝对过期时间, 优先级比Cache-Control低, 同时设置Expires和Cache-Control则后者生效.

Last-Modified
> 该资源的最后修改时间, 在浏览器下一次请求资源时, 浏览器将先发送一个请求到服务器上, 并附上If-Unmodified-Since头来说明浏览器所缓存资源的最后修改时间, 如果服务器发现没有修改, 则直接返回304(Not Modified)回应信息给浏览器(内容很少), 如果服务器对比时间发现修改了, 则照常返回所请求的资源.

> Last-Modified属性通常和Expires或Cache-Control属性配合使用, 因为即使浏览器设置缓存, 当用户点击”刷新”按钮时, 浏览器会忽略缓存继续向服务器发送请求, 这时Last-Modified将能够很好的减小回应开销.
