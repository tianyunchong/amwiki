### 引入js和css文件
```php
//控制器引入管理
$this->assets->addCss("static/css/jquery.tagbox.css");
//模板文件中引入
<?php $this->assets->outputCss('brandtort') ?>
```
