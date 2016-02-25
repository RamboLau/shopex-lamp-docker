# Shopex LAMP PHP5.3.29 Docker

CentOS verison: 6.7

Apache version: 2.2.29

Mysql verison: 5.1

PHP verison: 5.3.29

Root password: LNMP123

关于配置文件以及相关目录说明
apache: 
配置文件目录 /etc/httpd/conf/httpd.conf

php:
配置文件  /etc/php.ini
php 扩展配置文件目录 /etc/php.d/
zend 配置文件   /etc/php.d/Zend.ini

mysql5.1:
basedir /usr/local/mysql51
datadir /data/mysql/3306
配置文件 /usr/local/mysql51/my.cnf

php-pthreads:
basedir /usr/local/php-pthreads

memcache:
配置文件 /etc/sysconfig/memcached

redis :
配置文件 /etc/redis.conf

关于启动命令
apache 
service httpd start
mysql51
service mysql51 start
memcache
service memcached start
redis
service redis start

## Usage

```docker pull registry.aliyuncs.com/max/shopex-repo-lamp-php5.3.29```

```docker run --restart=always -e VIRTUAL_HOST=test1.test.com -P -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.3.29 ./run.sh```

```docker run --restart=always -P -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.3.29 ./run.sh```

```docker run --restart=always -e VIRTUAL_HOST=test1.test.com -p 30000:80 -p 30001:21 -p 30002:22 -p 30003:3306 -p 30004:6379 -p 30005:11211 -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.3.29 ./run.sh```


# Shopex LAMP PHP5.6 Docker

CentOS verison: 6.7

Apache version: 2.2.29

Mysql verison: 5.1

PHP verison: 5.6

Root password: LNMP123

关于配置文件以及相关目录说明
apache: 
配置文件目录 /etc/httpd/conf/httpd.conf

php:
配置文件  /etc/php.ini
php 扩展配置文件目录 /etc/php.d/
zend 配置文件   /etc/php.d/Zend.ini

mysql5.1:
basedir /usr/local/mysql51
datadir /data/mysql/3306
配置文件 /usr/local/mysql51/my.cnf

php-pthreads:
basedir /usr/local/php-pthreads

memcache:
配置文件 /etc/sysconfig/memcached

redis :
配置文件 /etc/redis.conf

关于启动命令
apache 
service httpd start
mysql51
service mysql51 start
memcache
service memcached start
redis
service redis start

## Usage

```docker pull registry.aliyuncs.com/max/shopex-repo-lamp-php5.6```

```docker run --restart=always -e VIRTUAL_HOST=test1.test.com -P -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.6 ./run.sh```

```docker run --restart=always -P -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.6 ./run.sh```

```docker run --restart=always -e VIRTUAL_HOST=test1.test.com -p 30000:80 -p 30001:21 -p 30002:22 -p 30003:3306 -p 30004:6379 -p 30005:11211 -ti --name LAMP registry.aliyuncs.com/max/shopex-repo-lamp-php5.6 ./run.sh```