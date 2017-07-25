### php链接mongo数据
```php
//简单链接
$dsn = 'mongodb://192.168.8.188:27017';
$mongo = new Client(
        $dsn,
        [],
        [
            'typeMap' => [
                'array'    => 'array',
                'document' => 'array',
                'root'     => 'array',
            ],
        ]);
return $mongo->selectDatabase($dbName);
//需要走验证的链接
$dsn = sprintf(
          'mongodb://%s:%s@%s:%s/?authMechanism=%s',
          $di['config']->statisticsMongo->username,
          $di['config']->statisticsMongo->password,
          $di['config']->statisticsMongo->host,
          $di['config']->statisticsMongo->port,
          $di['config']->statisticsMongo->authMechanism
      );
$mongo = new Client(
        $dsn,
        [],
        [
            'typeMap' => [
                'array'    => 'array',
                'document' => 'array',
                'root'     => 'array',
            ],
        ]);
return $mongo->selectDatabase($dbName);
```
