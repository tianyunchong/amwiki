### mongoClient使用
####链接
```php
$dsn = sprintf(
       'mongodb://%s:%s@%s:%s/?authMechanism=%s',
       $mongoConfig["username"],
       $mongoConfig["password"],
       $mongoConfig["host"],
       $mongoConfig["port"],
       $mongoConfig["authMechanism"]
);
$this->mongoClient = new \MongoClient($dsn);
```
####查询一条记录
```php
$collection = $this->mongoClient->selectDB("supsite")->selectCollection("data_resource");
$res = $collection->findOne(array("siteid" => new MongoId($siteid)));
```
####删除记录
```php
$collection->remove(array(
      "_id" => $res["_id"],
));
```
