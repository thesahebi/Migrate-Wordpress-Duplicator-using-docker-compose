# WordPress Docker Compose

This repository contains a Docker Compose configuration to set up a WordPress site with a MySQL database, including custom PHP settings.

## Usage

To start the services, run:
```sh
docker-compose up -d

```sh
WordPress will be available at http://localhost:5001.

Services
WordPress: The WordPress application, using the latest image.
MySQL: A MySQL database for WordPress.

Custom PHP Settings
A custom-php.ini file is included in the repository to allow for custom PHP settings. This file is mounted into the WordPress container to override the default PHP settings.

Example of custom-php.ini:
```sh
upload_max_filesize = 100M
post_max_size = 100M
memory_limit = 512M
***
You can modify the custom-php.ini file to suit your needs.


