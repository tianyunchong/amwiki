处理html标签短缺
```php
function stringTidy($str) {
    $config = array(
        'indent' => TRUE, //是否缩进
        'output-xhtml' => TRUE,//是否是输出xhtml
        'show-body-only'=>TRUE,//是否只获得到body
        'wrap' => 200
    );
    $tidy = tidy_parse_string($str, $config, 'UTF8');
    $tidy->cleanRepair();
    return $tidy;
}
```
