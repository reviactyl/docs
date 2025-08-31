---
icon: wrench
---

# Troubleshooting

## White screen after installation

You might see follow errors

* An error encountered while rendering this view. Try refreshing this page.

```bash
php artisan view:clear
```

## 500 Server Error

```bash
chmod -R 755 storage/* bootstrap/cache
php artisan view:clear
php artisan migrate --force
php artisan optimize

# If using NGINX or Apache (not on CentOS)
chown -R www-data:www-data /var/www/pterodactyl/*
# If using NGINX on CentOS
chown -R nginx:nginx /var/www/pterodactyl/*
# If using Apache on CentOS
chown -R apache:apache /var/www/pterodactyl/*
```

If these commands doesn't fix the error, set `APP_DEBUG=` to true, and then run;

```bash
php artisan config:clear
```

The debug for following error will be displayed.
