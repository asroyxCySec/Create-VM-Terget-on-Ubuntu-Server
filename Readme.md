# Langkah Awal Setelah Instalasi <br>

[![Tonton Video](https://img.youtube.com/vi/NoiIDszhnyI/hqdefault.jpg)](https://www.youtube.com/watch?v=NoiIDszhnyI)

## Update sistem terlebih dahulu:
```bash
sudo apt update && sudo apt upgrade -y
```
<br>

## Update sistem terlebih dahulu: <br>
### Text Editor:
```bash
sudo apt install vim nano -y
```
### Network Tools:
```bash
sudo apt install net-tools curl wget -y
```
### Build Essential (untuk kompilasi):
```bash
sudo apt install build-essential -y
```
### Git untuk version control:
```bash
sudo apt install git -y
```
<br><br>

## Keamanan Dasar <br>
### Firewall (UFW):
```bash
sudo apt install ufw -y
sudo ufw enable
sudo ufw allow ssh  # Jika menggunakan SSH
```
### Fail2ban (proteksi brute force):
```bash
sudo apt install fail2ban -y
```

<br><br>

## Berdasarkan Kebutuhan Spesifik <br>
### Web Server:
> Nginx
```bash
sudo apt install nginx -y
```
> Apache
```bash
sudo apt install apache2 -y
```
### Database:
> MySQL
```bash
sudo apt install mysql-server -y
```
> PostgreSQL
```bash
sudo apt install postgresql postgresql-contrib -y
```
### Programming Languages:
> Python
```bash
sudo apt install python3 python3-pip -y
```
> Node.JS
```bash
sudo apt install nodejs npm -y

```
> PHP
```bash
sudo apt install php php-fpm -y
```
### Monitoring:
```bash
sudo apt install htop neofetch -y
```

<br>

## Konfigurasi SSH (jika diperlukan)
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
