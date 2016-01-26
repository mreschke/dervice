# Dervice

A dockerized service builder using Systemd and Dervicefiles

# Install

	cd /tmp
	wget https://raw.githubusercontent.com/mreschke/dervice/master/dervice
	sudo mv dervice /usr/local/bin
	sudo chmod a+x /usr/local/bin/dervice

# Dervicefile

Dervice is like vagrant or docker in that it uses your current project directory to look for a Dervicefile

Example:

	/var/www/laravel/Dervicefile
	/var/www/laravel/Dockerfile
	/var/www/laravel/docker-compose.yml
	/var/www/laravel/composer.json
	/var/www/laravel/vendors
	etc...

Instead of using `docker run` or `docker-compose up` you use the `dervice` script to handle the container,
which reads from the Dervicefile.

# Usage

Dervice is meant to be used with a single service from a single `Dockerfile`, or a single service
from a group of linked containers with `docker-compose`.

Examples of single Dockerfile services would be to run things like

* MySQL
* Samba
* ProFTPd
* Redis

Examples of a linked container service would be like

* Laravel app with mysql, redis, php-fpm, nginx linked containers.
* Wordpress with mysql, php-fpm, nginx linked containers.
* Any complex custom app that you need to dockerize as a single service

Since Dervice acts on the current directory, you can keep your simple single services
like MySQL and Samba in git and simply clone them to say `~/dervice/xyz`

For those complex custom apps, just install them where you normally would like `/var/www/laravel`.
For these apps, the actual code is `/var/www/laravelp` which is simply linked as a volume inside
the proper containers.  Simply navigating to `/var/www/my-laravel-app`

FIXME


# Samba Example

**Example of a Samba file sharing container as a service**

`~/docker/samba/Dervicefile`
FIXME




