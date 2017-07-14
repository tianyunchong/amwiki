### fastcgi
FastCGI像是一个常驻(long-live)型的CGI，它可以一直执行着，只要激活后，不会每次都要花费时间去fork一次
Fastcgi是CGI的升级版，一种语言无关的协议，用来沟通程序(如PHP, Python, Java)和Web服务器(Apache2, Nginx), 理论上任何语言编写的程序都可以通过Fastcgi来提供Web服务。 Fastcgi的特点是会在一个进程中依次完成多个请求，以达到提高效率的目的，大多数Fastcgi实现都会维护一个进程池
