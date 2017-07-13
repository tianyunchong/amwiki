### eventloop
http://www.ruanyifeng.com/blog/2013/10/event_loop.html

新增加了一个消息线程，主要负责i/0操作，遇到io时，主线程通知event loop通知相应的i/0程序，接着往下执行，不存在红色等待时间,i/0程序完成后，event loop线程把结果返回给主线程，主线程调用事先设定的会调函数，完成任务，这种成为异步非阻塞模式
