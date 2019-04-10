# Docker Image with PHP extensions

[![Build Status](https://travis-ci.org/104corp/docker-php-testing.svg?branch=master)](https://travis-ci.org/104corp/docker-php-testing)
[![](https://img.shields.io/docker/stars/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)
[![](https://img.shields.io/docker/pulls/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)

See [Docker Hub](https://hub.docker.com/r/104corp/php-testing/)

## Supported tags and respective `Dockerfile` links

* [`7.3` (7.3/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.3/Dockerfile)
* [`7.3-apache` (7.3/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.3/apache/Dockerfile)
* [`7.2` (7.2/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.2/Dockerfile)
* [`7.2-apache` (7.2/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.2/apache/Dockerfile)
* [`7.1` (7.1/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.1/Dockerfile)
* [`7.1-apache` (7.1/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.1/apache/Dockerfile)
* [`7.0` (7.0/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.0/Dockerfile)
* [`7.0-apache` (7.0/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.0/apache/Dockerfile)
* [`5.6` (5.6/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.6/Dockerfile)
* [`5.6-apache` (5.6/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.6/apache/Dockerfile)
* [`5.5` (5.5/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.5/Dockerfile)
* [`5.5-apache` (5.5/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.5/apache/Dockerfile)

## Extensions

* exif
* gd
* mcrypt (not supported in PHP 7.2)
* memcached (using 2.2.0 in PHP 5.x)
* pdo_mysql
* redis
* soap
* zip

## Tools

* [Composer](https://getcomposer.org/) with [`hirak/prestissimo`](https://github.com/hirak/prestissimo) parallel install plugin
