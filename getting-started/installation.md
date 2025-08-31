---
icon: folder-arrow-down
---

# Installation

## Installing Pterodactyl Panel

**Kindly Refer** [**pterodactyl documentation**](https://pterodactyl.io/panel/1.0/getting_started.html) **before proceeding with Reviactyl installation.**

## Installing Required Dependencies

Installing NodeJS 16:

```bash
# Ubuntu/Debian
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install -y nodejs

# CentOS
curl -sL https://rpm.nodesource.com/setup_16.x | sudo -E bash -
sudo yum install -y nodejs yarn # CentOS 7
sudo dnf install -y nodejs yarn # CentOS 8, Rocky Linux 8, AlmaLinux 8
```

Installing yarn:

```bash
npm i -g yarn # Install Yarn
```

## Installing Reviactyl

Download the `reviactyl.zip`  from our [resources page](https://devnex.pro/resources/resource/10-revix-theme-for-pterodactyl/).&#x20;

Extract `reviactyl.zip` to **root** directory of pterodactyl (Ex; /var/www/pterodactyl)

```bash
cd /var/www/pterodactyl
chmod +x install.sh
./install.sh
php artisan view:clear
```

Our Script automatically installs Revix to your system. If there are any problems, kindly join [our discord server](https://discord.gg/ZrRsNKK94R).
