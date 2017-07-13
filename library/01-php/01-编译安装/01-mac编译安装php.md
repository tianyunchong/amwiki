### 准备工作
```shell
brew install gettext
brew install mcrypt libmcrypt
```

### 下载php
```shell
 wget http://php.net/distributions/php-5.6.31.tar.gz
 tar zxvf php-5.6.31.tar.gz
 cd php-5.6.31
 #编辑configure文件
 #找到 $PHP_GETTEXT /usr/local /usr 在后面加上gettext的路径 $PHP_GETTEXT /usr/local /usr /usr/local/opt/gettext

 ```

### 编译安装
```shell
./configure --prefix=/usr/local/php --enable-fpm  --with-mcrypt=/usr/local/libmcrypt --with-zlib --enable-mbstring --with-openssl --with-mysql --with-mysqli --with-mysql-sock --with-gd --with-jpeg-dir=/usr/lib --enable-gd-native-ttf  --enable-pdo --with-pdo-mysql --with-gettext --with-curl --with-pdo-mysql --enable-sockets --enable-bcmath --enable-xml --with-bz2 --enable-zip --enable-freetype
sudo make
sudo make install
```
