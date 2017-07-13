### php调用
```php
/** 创建链接 */
$esConfig = $this->di["config"]->smEs->toArray(); $hosts = array($esConfig["host"].":".$esConfig["port"]); $client = ClientBuilder::create()->setHosts($hosts)->build();
/** 建立查询json */
 $params          = array();
 $params["index"] = "supplieropalias";
 $params["type"]  = "supplierinfo";
 $params["body"]  = array(
	"query"   => array(
		 "match" => array(
		 "product" => $keyword,
 		),
 	),
 	"_source" => $columns,
 	"from"    => $offset,
 	"size"    => $limit,
 );
 return $params;
```
