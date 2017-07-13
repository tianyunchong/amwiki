```php
$di->setShared("mongo", function(){
    $mongoConfig = $this->getConfig()->mongo;
    return (new Client("mongodb://{$mongoConfig->host}:{$mongoConfig->port}/?replicaSet={$mongoConfig->replicaSet}"))
        ->selectDatabase($mongoConfig->database);
});
```
想使用Phalcon中的 ODM ，原来是引用 use Phalcon\Mvc\Collection; 并继承
