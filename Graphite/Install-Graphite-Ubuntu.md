## How to install Graphite on Ubuntu

### Update and Upgrade Ubuntu

```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo reboot
```

### Install the components

```
$ sudo apt-get install mysql-server
$ sudo apt-get install python-mysqldb
$ sudo apt-get install python-pymysql
$ sudo apt-get install graphite-web
$ sudo apt-get install graphite-carbon
$ sudo apt-get install apache2
$ sudo apt-get install libapache2-mod-wsgi
$ sudo apt-get install apt-transport-https
```

### Connect to MySql

```
$ sudo mysql -p
```

### Create the user and the database

```
CREATE USER 'graphite' IDENTIFIED BY 'password';
CREATE DATABASE IF NOT EXISTS `graphite` DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
GRANT ALL PRIVILEGES ON `graphite`.* TO 'graphite'@'localhost';
```

### Update Graphite’s config file

Open the config file

```
sudo nano /etc/graphite/local_settings.py
```

Change the Secret Key

```
Find “SECRET_KEY” and change its value to a long secret key
```

Change the Time Zone

```
Find “TIME_ZONE” and change its value to a relevant time zone in the format of
Country/City e.g. Australia/Sydney
```

Configure the database

```
DATABASES = {
    'default': {
        'NAME': 'graphite',
        'ENGINE': 'django.db.backends.mysql',
        'USER': 'graphite',
        'PASSWORD': 'password',
        'HOST': '127.0.0.1',
        'PORT': '3306',
        'STORAGE_ENGINE': 'INNODB'
    }
}
```

Replace the database name, user name and password for your own database details.

Quit Nano

```
1. Press Ctrl (or command) button + O to save the config file.
2. Press Ctrl (or command) + X to exit
```

### Sync the database

```
1- sudo graphite-manage syncdb
2- sudo graphite-manage syncdb (repeat the command)
```

### Enable caching in Carbon

```
sudo nano /etc/default/graphite-carbon
```

Then change the false value to true:

```
CARBON_CACHE_ENABLED=true
```

### Launch Carbon’s caching service

```
sudo systemctl start carbon-cache
```

### Launch Graphite Web

```
a2dissite 000-default
sudo cp /usr/share/graphite-web/apache2-graphite.conf /etc/apache2/sites-available
```

### Use port 8888 for Graphite
```
sudo nano /etc/apache2/sites-available/apache2-graphite.conf
```

In the VirtualHost element, change 80 to 8888:
<VirtualHost *:8888>
Press Ctrl (or command) + O to save
Press Ctrl (or command) + X to exit

### Add 8888 to Apache ports

```
sudo nano /etc/apache2/ports.conf
```

Listen 80
Listen 8888
Press Ctrl (or command) + O to save
Press Ctrl (or command) + X to exit

### Start Graphite Web

```
a2ensite apache2-graphite
systemctl restart apache2
```

Navigate to your Graphite web:

http://your-address:8888

<img width=600 src="https://user-images.githubusercontent.com/44635266/64627224-338b6880-d42a-11e9-8565-a18185d42a3c.png">