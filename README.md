# Docker for Magento [![Build Status](https://travis-ci.org/ajardin/docker-symfony.svg?branch=master)](https://travis-ci.org/ajardin/docker-symfony)
This repository allows the creation of a Docker environment that meets [Symfony3](http://symfony.com/doc/current/reference/requirements.html) requirements.

## Architecture
```bash
$ docker-compose ps
     Name                   Command             State              Ports
-----------------------------------------------------------------------------------
symfony_mysql_1   docker-entrypoint.sh mysqld   Up      0.0.0.0:3306->3306/tcp
symfony_nginx_1   nginx -g daemon off;          Up      443/tcp, 0.0.0.0:80->80/tcp
symfony_node_1    node                          Up      0.0.0.0:8888->8888/tcp
symfony_php_1     php-fpm                       Up      0.0.0.0:9000->9000/tcp
```

## Installation

Clone or download this repo, then: 
```bash
$ docker-compose up
```
