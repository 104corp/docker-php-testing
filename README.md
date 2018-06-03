# Docker Image with PHP extensions

[![Build Status](https://travis-ci.org/104corp/docker-php-testing.svg?branch=master)](https://travis-ci.org/104corp/docker-php-testing)
[![](https://img.shields.io/docker/stars/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)
[![](https://img.shields.io/docker/pulls/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)

See [Docker Hub](https://hub.docker.com/r/104corp/php-testing/)

## Supported tags and respective `Dockerfile` links

* [`7.2` (7.2/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.2/Dockerfile)
* [`7.1` (7.1/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.1/Dockerfile)
* [`7.0` (7.0/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.0/Dockerfile)
* [`5.6` (5.6/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.6/Dockerfile)
* [`5.5` (5.5/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/5.5/Dockerfile)

## Extensions

* exif
* gd
* mcrypt (not supported in PHP 7.2)
* memcached (using 2.2.0 in PHP 5.x)
* pdo_mysql
* soap
* zip

## Tools

* [Composer](https://getcomposer.org/) with [`hirak/prestissimo`](https://github.com/hirak/prestissimo) parallel install plugin
