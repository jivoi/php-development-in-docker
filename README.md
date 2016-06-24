# Pre-requisites

You must have Docker installed for this code to work! Check the [Installation Guide](https://docs.docker.com/engine/installation/) if you haven't got it installed.

It contains a basic LEMP stack running with Docker, intented to be used for local web development.

## Get started

Clone the project and run docker-compose

```bash
git clone https://github.com/jivoi/php-development-in-docker.git
cd php-development-in-docker
docker-compose up -d
docker-machine ip default
docker-compose -d down
```

## Description

The different containers are described in [`docker-compose.yml`](https://github.com/jivoi/php-development-in-docker/blob/master/docker-compose.yml).

There are 6 of them:

 - a container for Nginx
 - a container for PHP-FPM
 - a container for MySQL
 - a container for phpMyAdmin
 - a container to make MySQL data persistent
 - a container for the application code

All of them are using official images.

The current directory is mounted into the one served by Nginx on the container, so any update to the code is available without having to rebuild the container.

The MySQL data sits in its own directory mounted into its own container to make it persistent.

The application is available on the port 80 of the host machine.

phpMyAdmin is available on port 8080.
