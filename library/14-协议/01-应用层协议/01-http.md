### http
1. HTTP属于TCP/IP应用层协议,应用层协议有很多，比如HTTP、FTP、TELNET等，也可以自己定义应用层协议。
2. WEB使用HTTP协议作应用层协议，以封装HTTP文本信息，然后使用TCP/IP做传输层协议将它发到网络上。
> HTTP协议是建立在请求/响应模型上的。首先由客户建立一条与服务器的TCP链接，并发送一个请求到服务器，请求中包含请求方法、URI、协议版本以及相关的MIME样式的消息。服务器响应一个状态行，包含消息的协议版本、一个成功和失败码以及相关的MIME式样的消息。
3. http1.0和1.1的区别
> HTTP/1.0为每一次HTTP的请求/响应建立一条新的TCP链接，因此一个包含HTML内容和图片的页面将需要建立多次的短期的TCP链接。一次TCP链接的建立将需要3次握手。但HTTP/1.1里面有所改变,可以在一次连接中处理多个请求，并且多个请求可以重叠进行，不需要等待一个请求结束后再发送下一个请求。

由于HTTP在每次请求结束后都会主动释放连接，因此HTTP连接是一种“短连接”，要保持客户端程序的在线状态，需要不断地向服务器发起连接请求。通常的做法是即时不需要获得任何数据，客户端也保持每隔一段固定的时间向服务器发送一次“保持连接”的请求，服务器在收到该请求后对客户端进行回复，表明知道客户端“在线”。若服务器长时间无法收到客户端的请求，则认为客户端“下线”，若客户端长时间无法收到服务器的回复，则认为网络已经断开。

------------

http协议基于tcp协议，发送http请求需要先保证tcp连接上(tcp的三次握手)，http发送请求后，会通过tcp建立y一个到服务器的通道，当http请求发送完毕后并获取到服务器返回的数据，http会立即断开tcp，所以http是个短连接，但是tcp是个长连接

------------

TCP是底层通讯协议，定义的是数据传输和连接方式的规范

HTTP是应用层协议，定义的是传输数据的内容的规范

HTTP协议中的数据是利用TCP协议传输的，所以支持HTTP也就一定支持TCP
