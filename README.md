# docker-php-composer-mysql-nginx
A php (5.6>), composer, mysql, nginx docker compose configuration

It's a docker compose config that let's you build a developement environment quickly for a new project.

## Install

```sh
git clone https://github.com/balintsera/docker-php-composer-mysql-nginx.git newproject
cd newproject # change dir to the repo
rm -rf .git # remove .git since you don't want to push to this repo (probably, but every pull request is welcome)
docker-compose up # build docker containers
```

## Containers

This docker-compose config builds 3 containers:
  1. A php-fpm that runs on port 9000
  2. An nginx webserver that binds to php-fpm
  3. A mysql database to your app db

In the php-fpm one there is composer installed, so you can install your projects dependencies inside of your container. The nginx document root is set to `/public`.

Both php and nginx have an editable config files in `/dockerfiles` directory (nginx/ and php-fpm/).

## Usage example

Install and run docker-compose up. Create a directory called `src` on the root. This will hold your files.

If you need composer to install, exec the php-fpm container, cd to the src dir and run `composer install wathever/youneed`

 
