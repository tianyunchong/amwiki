### assets
Phalcon\Assets是一个让开发者管理静态资源的组件，如管理css，JavaScript等
引入使用
```php
$di->setShared("assets", function () use ($di) {
      return new \Phalcon\Assets\Manager();
});
```
