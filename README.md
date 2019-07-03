# LEMP stack built with Docker Compose

This is a basic LEMP stack environment built using Docker Compose. It consists following:

* PHP-FPM
* Nginx
* MySQL 5.7
* PhpMyAdmin
* Redis

As of now, we have 4 different branches for different PHP versions. Use appropriate branch as per your php version need:
* [5.6.x](https://github.com/gehlotanish/nginx-phpfpm/tree/fpm-5.6.x)
* [7.1.x](https://github.com/gehlotanish/nginx-phpfpm/tree/fpm-7.1.x)
* [7.2.x](https://github.com/gehlotanish/nginx-phpfpm/tree/fpm-7.2.x)
* [7.3.x](https://github.com/gehlotanish/nginx-phpfpm/tree/fpm-7.3.x)
* [Multi-fpm](https://github.com/gehlotanish/nginx-phpfpm/tree/multi_fpm)

Master baranch can execute different php-fpm version based on nginx configuration on single code in www directory.

## Installation

Clone this repository on your local computer and checkout the appropriate branch e.g. 7.x.x. Run the `docker-compose up -d`.

```shell
git clone https://github.com/gehlotanish/nginx-phpfpm.git        
cd docker-php/
git fetch --all
cd bin/ 
bash install-docker.sh
bash install-docker-compose.sh
git checkout fpm-7.x.x
docker-compose up -d
```

Your LEMP stack is now ready!! You can access it via `http://localhost`.

## Connect via SSH

You can connect to web server using `docker exec` command to perform various operation on it. Use below command to login to container via ssh.

```shell
docker exec -it webserver /bin/bash
docker exec -it mysql /bin/bash
```

## Configuration

This package comes with default configuration options. You can modify them by creating `.env` file in your root directory.

To make it easy, just copy the content from `sample.env` file and update the environment variable values as per your need.

## phpMyAdmin

phpMyAdmin is configured to run on port 8080. Use following default credentials.

```shell
http://localhost:8000/
```

## Redis

It comes with Redis. It runs on default port `6379`.

## Configuration and Usage

Please read from appropriate version branch.
