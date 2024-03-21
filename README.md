# UbuntuInstalacions

## Personalizacion
https://www.youtube.com/watch?v=qC0mnGprbeM
-letras mononoki y roboto

https://www.youtube.com/watch?v=PO_1i_Uh9As

https://www.youtube.com/watch?v=lXIb-1_H-mA&t=61s

## Apache
```
- sudo apt update
- sudo apt install apache
```

apache error php 8.2
https://www.digitalocean.com/community/tutorials/apache-configuration-error-ah00558-could-not-reliably-determine-the-server-s-fully-qualified-domain-name


## PHP diferentes versiones y diferentes formas de setearlo
https://devanswers.co/run-multiple-php-versions-on-apache/
```
- sudo apt install php8.2 php8.2-fpm php8.2-mysql libapache2-mod-php8.2
- sudo apt install php8.1 php8.1-fpm php8.1-mysql libapache2-mod-php8.1
- sudo apt install php8.0 php8.0-fpm php8.0-mysql libapache2-mod-php8.0
- sudo apt install php7.0 php7.0-fpm php7.0-mysql libapache2-mod-php7.0
- sudo apt install php7.4 php7.4-fpm php7.4-mysql libapache2-mod-php7.4
- sudo apt install php6 php6-fpm php6-mysql libapache2-mod-php6
- sudo apt install php5.6 php5.6-fpm php5.6-mysql libapache2-mod-php5.6

- sudo apt install php8.2-common php8.2-mysql php8.2-xml php8.2-xmlrpc php8.2-curl php8.2-gd php8.2-imagick php8.2-cli php8.2-dev php8.2-imap php8.2-mbstring php8.2-opcache php8.2-soap php8.2-zip php8.2-intl -y
- sudo apt install php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-intl -y
- sudo apt install php8.0-common php8.0-mysql php8.0-xml php8.0-xmlrpc php8.0-curl php8.0-gd php8.0-imagick php8.0-cli php8.0-dev php8.0-imap php8.0-mbstring php8.0-opcache php8.0-soap php8.0-zip php8.0-intl -y
- sudo apt install php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap php7.4-zip php7.4-intl -y
- sudo apt install php7.0-common php7.0-mysql php7.0-xml php7.0-xmlrpc php7.0-curl php7.0-gd php7.0-imagick php7.0-cli php7.0-dev php7.0-imap php7.0-mbstring php7.0-opcache php7.0-soap php7.0-zip php7.0-intl -y
- sudo apt install php6-common php6-mysql php6-xml php6-xmlrpc php6-curl php6-gd php6-imagick php6-cli php6-dev php6-imap php6-mbstring php6-opcache php6-soap php6-zip php6-intl -y
- sudo apt install php5.6-common php5.6-mysql php5.6-xml php5.6-xmlrpc php5.6-curl php5.6-gd php5.6-imagick php5.6-cli php5.6-dev php5.6-imap php5.6-mbstring php5.6-opcache php5.6-soap php5.6-zip php5.6-intl -y

  sudo apt-get install mcrypt php5-mcrypt
```
### .htaccess
```
<FilesMatch \.php>
    # Apache 2.4.10+ can proxy to unix socket
    SetHandler "proxy:unix:/var/run/php/php8.2-fpm.sock|fcgi://localhost/"
</FilesMatch>
```
## instalacion de mysql
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04-es

## xdebug
https://xdebug.org/docs/install
First, you need to update local packages using the following command:

sudo apt update
# OR
sudo apt-get update
Now you can install xdebug with the following command:

sudo apt install php-xdebug
And configure it as:

sudo nano /etc/php/7.0/mods-available/xdebug.ini

```
zend_extension=/usr/lib/php/20151012/xdebug.so
xdebug.remote_autostart = 1
xdebug.remote_enable = 1
xdebug.remote_handler = dbgp
xdebug.remote_host = 127.0.0.1
xdebug.remote_log = /tmp/xdebug_remote.log
xdebug.remote_mode = req
xdebug.remote_port = 9005 #if you want to change the port you can change 
```
And then restart the services:
```
sudo systemctl restart php7.0-fpm
sudo systemctl restart nginx # If you are using nginx server
sudo systemctl restart apache2 # If you are using apache server
```

```
sudo apt-get install php8.2-xdebug
sudo apt-get install php8.1-xdebug
sudo apt-get install php8.0-xdebug
sudo apt-get install php7.4-xdebug
sudo apt-get install php7.0-xdebug
sudo apt-get install php6.0-xdebug
sudo apt-get install php5.6-xdebug
```
## phpMyAdmin
https://www.phpmyadmin.net/
unzip
mv /var/www/html/

## virtual host
```
<VirtualHost *:80>
    ServerName cursosplatzi.local
    DocumentRoot /home/eurizar/proyectos/cursos/platzi/backcend-php/4-intregrac>

   <Directory /home/eurizar/proyectos/cursos/platzi/backcend-php/4-intregracion>
      Options Indexes FollowSymLinks
      AllowOverride All
      Require all granted
      # SetEnvIf Authorization .+ HTTP_AUTORIZARION=$0
   </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

#vim: syntax=apache ts=4 sw=4 sts=4 sr noet
```
https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-20-04


error laravel redirection
https://www.nicesnippets.com/blog/the-requested-url-was-not-found-on-this-server-apache2441-in-ubuntu-2204
## apps

### composer
https://getcomposer.org/download/
### wp-cli
https://make.wordpress.org/cli/handbook/guides/installing/
### node 18
https://techviewleo.com/how-to-install-node-js-18-lts-on-ubuntu/

### git
```
sudo apt install git
```
si se quiere ver rama en consola 
```
sudo nano ~/.bashrc
```
copiar y pegar al final de bashrc
```
# Show git branch name in console

function gitbranch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}

PS1="\[\e[1;32m\]\u@\h:\[\e[1;34m\]\w \[\e[1;35m\]\$(gitbranch)\[\e[0;00m\]\$\[\e[0;00m\] "
```

# Error de mysql 8 com php antiguo 5.6 

para solicionar el error:

```
The server requested authentication method unknown to the client
```

en el path /etc/mysql/my.cnf pegar esta linea

```
[mysqld]
default_authentication_plugin=mysql_native_password

```

- vscode
- meld
- aptitude
- git
- gitk
- anchor para blockchain
- Eos bin
- wp cli
- composer
- symfony cli
- docker
- xdebug
- curl
- #agregar mas cosas segun me vaya recordando
- 
