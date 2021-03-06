# Actions and Docker Image with PHP extensions

[![GitHub Release](https://img.shields.io/github/tag/104corp/docker-php-testing.svg)](https://github.com/104corp/docker-php-testing/releases)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![DockerHub Stars](https://img.shields.io/docker/stars/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)
[![DockerHub Pulls](https://img.shields.io/docker/pulls/104corp/php-testing.svg)](https://hub.docker.com/r/104corp/php-testing/)

![Testing](https://github.com/104corp/docker-php-testing/workflows/Testing/badge.svg)
![Publish Docker](https://github.com/104corp/docker-php-testing/workflows/Publish%20Docker/badge.svg)

## Usage for Actions

Via GitHub Workflow

```
- name: PHP testing actions
  uses: 104corp/docker-php-testing@master
```

## Usage for Docker

See [Docker Hub](https://hub.docker.com/r/104corp/php-testing/)

## Supported tags and respective `Dockerfile` links

* [`8.0` (8.0/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/8.0/Dockerfile)
* [`8.0-apache` (8.0/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/8.0/apache/Dockerfile)
* [`7.4` (7.4/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.4/Dockerfile)
* [`7.4-apache` (7.4/apache/Dockerfile)](https://github.com/104corp/docker-php-testing/blob/master/7.4/apache/Dockerfile)
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

* bcmath
* exif
* gd
* gmp
* mcrypt (not supported in PHP 7.2+)
* memcached (using 2.2.0 in PHP 5.x)
  + [2.2.0](https://pecl.php.net/package/memcached/2.2.0) in PHP 5.x
* pdo_mysql
* [redis](https://pecl.php.net/package/redis)
  + 5.0+ in PHP 7.x
  + [4.3.0](https://pecl.php.net/package/redis/4.3.0) in PHP 5.x
* soap
* sockets
* zip

## Tools

* GNU Make
