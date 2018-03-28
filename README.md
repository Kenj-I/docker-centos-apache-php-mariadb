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
//.env

VIRTUAL_HOST=
HOST_DB_PORT=
```

```envfile
MYSQL_ROOT_PASSWORD=
MYSQL_DATABASE=
MYSQL_USER=
MYSQL_PASSWORD=

DATABASE_HOST=
DATABASE_NAME=
DATABASE_USER=
DATABASE_PASSWORD=
FUEL_ENV=
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
