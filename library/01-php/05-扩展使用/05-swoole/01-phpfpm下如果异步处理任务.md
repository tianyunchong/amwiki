####
php-fpm/apache环境下只能使用同步客户端
但是可以使用某些办法达到同样的办法，比如在服务端onReceive中，创建task任务，同样是异步的效果
```php
$server->task($data, -1);
```
