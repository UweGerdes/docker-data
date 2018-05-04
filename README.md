# Docker uwegerdes/data

At the moment this data container shares the directory `/var/www/htdocs`.

This directory is used by my docker images `uwegerdes/php-fpm` and `uwegerdes/nginx` in my [`frontend-development`](https://github.com/UweGerdes/frontend-development) project.

## Build

Build the image with (mind the dot):

```bash
$ docker build -t uwegerdes/data .
```

## Usage

Make sure you have a htdocs directory in your current folder (`$(pwd)/htdocs`) or supply the absolute (not relative!) path to your desired web root:

```bash
$ docker run \
	-v $(pwd)/htdocs:/var/www/htdocs \
	--name data \
	uwegerdes/data
```

The command will create a container and exit. That is ok because only the volumes from the container will be used.

