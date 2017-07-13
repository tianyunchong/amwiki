```php
$headers = array(
        "Host:apis.xzcms.net",
);
$postData = array(
       "siteid" => "595f4a8be39acc6646679340",
       "taskid" => "59643470e39acc66470f13b4",
);
post("http://192.168.8.165/themepackv2/index/sitemap/, $postData, $headers);
function post($url, $data, $header = array(), $timeOut = 3)
{
    $data    = empty($data) ? array() : (array) $data;
    $header  = empty($header) ? array() : (array) $header;
    $timeOut = empty($timeOut) ? 0 : (int) $timeOut;
    $curl    = curl_init();
    curl_setopt($curl, CURLOPT_URL, $url);
    curl_setopt($curl, CURLOPT_USERAGENT, 'Mozilla/5.0 (Windows; U; Windows NT 5.1; .' .
    'zh-CN; rv:1.9.2.8) Gecko/20100722 Firefox/3.6.8');
    curl_setopt($curl, CURLOPT_CONNECTTIMEOUT, $timeOut);
    curl_setopt($curl, CURLOPT_TIMEOUT, $timeOut);
    curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($curl, CURLOPT_POST, 1);
    if (!isset($data['is_file'])) {
        curl_setopt($curl, CURLOPT_POSTFIELDS, http_build_query($data));
    } else {
        curl_setopt($curl, CURLOPT_POSTFIELDS, $data);
    }
    if ($header) {
        curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($curl, CURLOPT_HTTPHEADER, $header);
    }
    $str      = curl_exec($curl);
    $httpCode = curl_getinfo($curl, CURLINFO_HTTP_CODE);
    curl_close($curl);
    return $str;
}
```
