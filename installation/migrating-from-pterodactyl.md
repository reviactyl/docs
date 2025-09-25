---
icon: desktop-arrow-down
---

# Migrating From Pterodactyl

{% hint style="info" %}
**Reviactyl** is backwards compatible with pterodactyl. This means no data loss from switching over between Pterodactyl & Reviactyl.
{% endhint %}

You will need to have root access to your server in order to run and use this panel.

## Remove Pterodactyl Old Files

{% hint style="warning" %}
**PRE-CAUTION!**\
Make sure you have saved your `.env` file somewhere else incase risk of losing `.env` during migration.
{% endhint %}

```sh
cd /var/www/pterodactyl
rm -rf *
```

## Download & Install Latest Version of Reviactyl

```sh
cd /var/www/pterodactyl
curl -Lo panel.tar.gz https://github.com/reviactyl/panel/releases/latest/download/panel.tar.gz
tar -xzvf panel.tar.gz
chmod -R 755 storage/* bootstrap/cache/
```

## Download Composer Dependencies

```sh
COMPOSER_ALLOW_SUPERUSER=1 composer install --no-dev --optimize-autoloader
```

## Run Database Migrations

```sh
php artisan migrate --seed --force
```

## Set Permissions

```sh
# If using NGINX, Apache or Caddy (not on RHEL / Rocky Linux / AlmaLinux)
chown -R www-data:www-data /var/www/pterodactyl/*

# If using NGINX on RHEL / Rocky Linux / AlmaLinux
chown -R nginx:nginx /var/www/pterodactyl/*

# If using Apache on RHEL / Rocky Linux / AlmaLinux
chown -R apache:apache /var/www/pterodactyl/*
```

## Restart Queue Worker

```sh
sudo systemctl restart pteroq.service
```

Thats it! Just easy as that.
