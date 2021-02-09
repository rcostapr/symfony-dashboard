# Symfony Free Dashboard

## Composer

### Update to Version 2

-   sudo composer self-update

## PHP Change Version

### Show Versions

-   ls -la /usr/bin | grep php
-   sudo update-alternatives --config php

### Set Version

-   sudo update-alternatives --set php /usr/bin/php7.4
-   sudo update-alternatives --set php /usr/bin/php8.0

## Install PHP 8.0 with CLI

-   sudo apt install php8.0-common php8.0-cli -y

### Install Server APIs

Depending on the web server you use, you will need to install additional packages to integrate with the web server.

For Apache using mpm_event, Nginx, Litespeed, etc., php8.0-fpm package provides integration with PHP 8.0 via FPM.

-   sudo apt install php8.0-fpm

For Apache using mod_php, install libapache2-mod-php8.0.

-   sudo apt install libapache2-mod-fcgid
-   sudo apt install libapache2-mod-php8.0

### install useful extensions

-   sudo apt install php8.0-{bz2,curl,intl,mysql,readline,xml}
-   php -v # Show PHP version.
-   php -m # Show PHP modules loaded.

```
NOTICE: Not enabling PHP 8.0 FPM by default.
NOTICE: To enable PHP 8.0 FPM in Apache2 do:
NOTICE: sudo a2enmod proxy_fcgi setenvif
NOTICE: sudo a2enconf php8.0-fpm
NOTICE: To activate the changes, restart Apache: $systemctl restart apache2 .
```

-   sudo apt install php8.0-pcov # PCOV code coverage tool
-   sudo apt install php8.0-xdebug # Xdebug debugger

### Purge old PHP versions

-   sudo apt purge '^php7.4.\*'

### List existing PHP packages

If you are updating from an existing PHP version to 8.0, it's important to get a list of existing PHP packages. Albeit the small extension changes, installing the PHP 8.0 counterpart packages is the easiest way to make sure the upgrade is smooth and covers the same packages from the current PHP version.

-   dpkg -l | grep php | tee packages.txt
