## netstat
### `·netstat -an`
> proto（连接方式）、local address（本地连接地址）、foreign address（和本地建立连接的地址）、state（当前端口状态）
> LISTEN：侦听来自远方的TCP端口的连接请求
> SYN-SENT：在发送连接请求后等待匹配的连接请求
> SYN-RECEIVED：在收到和发送一个连接请求后等待对方对连接请求的确认
> ESTABLISHED：代表一个打开的连接
> FIN-WAIT-1：等待远程TCP连接中断请求，或先前的连接中断请求的确认
> FIN-WAIT-2：从远程TCP等待连接中断请求
> CLOSE-WAIT：等待从本地用户发来的连接中断请求
> CLOSING：等待远程TCP对连接中断的确认
> LAST-ACK：等待原来的发向远程TCP的连接中断请求的确认
> TIME-WAIT：等待足够的时间以确保远程TCP接收到连接中断请求的确认
> CLOSED：没有任何连接状态

因为linux分配给一个用户的文件句柄是有限的，而TIME_WAIT和CLOSE_WAIT两种状态如果一直被保持，那么意味着对应数目的通道就一直被占着，而且是“占着茅坑不使劲”，一旦达到句柄数上限，新的请求就无法被处理了，接着就是大量Too Many Open Files异常，Tomcat崩溃。

### `netstat -tunp`
看到所有和本地计算机建立连接的IP

### 服务器连接状态
统计80端口连接数

`netstat -nat|grep -i "80"|wc -l`

统计httpd协议连接数

`ps -ef|grep httpd|wc -l`

统计已连接上的，状态为established

`netstat -na|grep ESTABLISHED|wc -l`

连接状态统计

`netstat -n | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'`
> SYN_RECV表示正在等待处理的请求数；

> ESTABLISHED表示正常数据传输状态；

> TIME_WAIT表示处理完毕，等待超时结束的请求数。
