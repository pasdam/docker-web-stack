# docker-web-stack

This repository contains a [docker-compose](docker-compose.yaml) file to start a
web stack with [nginx](https://www.nginx.com/), [php8](https://www.php.net/),
and [MySQL](https://www.mysql.com/), using **only official images**.

To run the stack:

```sh
docker-compose up
```

The website files should be in the folder `www`.

## Usage

Create a local `env` file with the required secrets:

```sh
cat << EOT > .local.env
MYSQL_ROOT_PASSWORD=your_mysql_root_password
EOT
```

then spin up the containers:

```sh
docker-compose up
```

At this point you should be able to access:

* the website at [localhost](http://localhost/): it should show a summary of the
  PHP config;
* phpmyadmin at [localhost:8080](http://localhost:8080/): you can login using
  `root` and the DB password in the env file created before.

## Legacy version

In case you need to run a stack with a legacy version of PHP 5 you can use the
`docker-compose-legacy.yml`, which uses an old PHP image.
