[![Tonton Video](https://img.youtube.com/vi/P8_NOnIBMw8/hqdefault.jpg)](https://www.youtube.com/watch?v=P8_NOnIBMw8)

# Step 1: Install LAMP Stack <br>

## Install Apache, MySQL, PHP:
```bash
sudo apt install apache2 mysql-server php php-mysql php-gd php-mbstring libapache2-mod-php -y
```
<br>

## Start dan enable services:
```bash
sudo systemctl start apache2
sudo systemctl enable apache2
sudo systemctl start mysql
sudo systemctl enable mysql
```
<br>

# Step 2: Secure MySQL Installation <br>

```bash
sudo mysql_secure_installation
```
<br>

> - Set root password (misalnya: root123)
> - Remove anonymous users: Y
> - Disallow root login remotely: Y
> - Remove test database: Y
> - Reload privilege tables: Y

<br> <br>

# Step 3: Download dan Setup DVWA <br>

## Download DVWA:
```bash
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git dvwa
sudo chown -R www-data:www-data dvwa/
sudo chmod -R 755 dvwa/
```
<br>

# Step 4: Setup Database <br>

## Masuk ke MySQL:
```bash
sudo mysql -u root -p
```
<br>

## Buat database dan user:
```bash
CREATE DATABASE dvwa;
CREATE USER 'dvwa'@'localhost' IDENTIFIED BY 'p@ssw0rd';
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
<br>

# Step 5: Konfigurasi DVWA <br>

## Copy dan edit config file:
```bash
cd /var/www/html/dvwa/config
sudo cp config.inc.php.dist config.inc.php
sudo nano config.inc.php
```
<br>

## Edit bagian database:
```bash
$_DVWA[ 'db_server' ]   = '127.0.0.1';
$_DVWA[ 'db_database' ] = 'dvwa';
$_DVWA[ 'db_user' ]     = 'dvwa';
$_DVWA[ 'db_password' ] = 'p@ssw0rd';
```
<br>

# Step 6: Konfigurasi PHP <br>

## Edit php.ini:
```bash
sudo nano /etc/php/8.1/apache2/php.ini
```
<br>

## Ubah setting berikut:
```bash
allow_url_fopen = On
allow_url_include = On
display_errors = On
```
<br>

Restart Apache:
```bash
sudo systemctl restart apache2
```
<br>

# Step 7: Akses DVWA
## Buka browser dan akses:
```bash
http://your-server-ip/dvwa/setup.php
```
<br>

> Klik "Create / Reset Database" untuk setup database.

<br>

# Step 8: Login ke DVWA <br>

## Default credentials:

> - Username: admin
> - Password: password
> - URL login: http://your-server-ip/dvwa/login.php

<br>

# Security Level <br>

Setelah login, Anda bisa mengatur security level di:
```bash
DVWA Security → Security Level
```

> - Low: Paling mudah, untuk pemula
> - Medium: Moderate protection
> - High: Lebih sulit
> - Impossible: Secure implementation
