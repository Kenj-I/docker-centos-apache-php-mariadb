# docker centos-apache-php-mariadb

## git clone

```shell
$ git clone git@github.com:Kenj-I/docker-centos-apache-php-mariadb.git
```

## init

```shell
$ cd docker-centos-apache-php-mariadb-development
$ sh init.sh
```

## write env

.env and build/envfile

if use nginx_proxy, set virtualhost and your hosts

```.env
//ex

VIRTUAL_HOST=hogehoge.local
HOST_DB_PORT=33306
```

## usage

UP

```shell
$ cd docker-centos-apache-php-mariadb-development/docker
$ docker-compose build
$ docker-compose start
```

```shell
$ docker-compose stop
```
