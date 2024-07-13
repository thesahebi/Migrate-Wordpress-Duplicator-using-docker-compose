# Migrate an existing WordPress site using Duplicator and docker-compose in your localhost or production.

If you've struggled with managing a WordPress website and creating a development version for ongoing development, there's a more straightforward solution using Docker Compose. This repository provides a sample setup that you can use in both production and development environments with minor adjustments to the YAML file.

This repository contains a Docker Compose configuration to set up an existing WordPress site using Duplicator for backup and migration.

## Usage

To start the services, run:

```sh

docker-compose up -d
```
To migrate an existing WordPress site using Duplicator, follow these steps:

    1- Create a Duplicator Package:
    
    From your existing WordPress site, create a Duplicator package (installer and archive files).
    
    2- Add Duplicator Files:
    Place the installer.php and archive file (*.zip) into the wordpress directory.
    
    3- Run Duplicator Installer:
    Access the installer by navigating to http://localhost:5001/installer.php and follow the on-screen instructions to complete the migration.

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
```
You can modify the custom-php.ini file to suit your needs.


Volumes
db_data: Stores MySQL data.
wp-data: Stores WordPress data.
Environment Variables
```sh
WORDPRESS_DB_HOST: Hostname of the database.
WORDPRESS_DB_USER: Username for the database.
WORDPRESS_DB_PASSWORD: Password for the database.
WORDPRESS_DB_NAME: Name of the database.
```

Create/Commit an issue ticket if you face anything during installation.

