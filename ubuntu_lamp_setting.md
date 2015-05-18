## apache2インストール
```
sudo apt-get update
sudo apt-get install apache2 
```
## mariadb10.0
```
1. apt-get install mariadb-server.
2. set root password.
3. mysql -uiroot -p
```

## PHP
```
sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt
```

## composerとlaravelのインストール
```
https://github.com/BoomLEE/document/blob/master/laravel_install.md

```

## mcrypt
```
sudo apt-get install mcrypt php5-mcrypt
sudo php5enmod mcrypt
sudo service apache2 restart
```

## apache2のdefault directory 設定
```
sudo vi 000-default.conf
sudo service apache2 restart
```

## permissions
```
php artisan cache:clear
sudo chmod -R 777 vendor/
sudo chmod -R 777 storage/

```

## command
```
service apache2 restart
```

## LINK
- [Install MariaDB on Ubuntu]
(https://www.vultr.com/docs/install-mariadb-on-ubuntu-14-04)
- [Ubuntu 14.04 LAMP setting]
(http://zaka-think.com/linux/ubuntu/ubuntu-14-04-lamp-setting/)
- [Ubuntu LAMP setting - vagrant box]
(https://atlas.hashicorp.com/db_lee/boxes/laravel/versions/1.0.0)
