// Package Installation
sudo apt install nginx mariadb-server mariadb-client php7.2 php7.2-fpm
sudo apt-get update
sudo apt install nginx mariadb-server mariadb-client php7.2 php7.2-fpm
sudo service nginx start
sudo service mysql start
sudo mysql_secure_installation
curl -4 icanhazip.com

// Nginx Server Setup
cd /etc/nginx/sites-available
sudo cp default midtest
sudo nano midtest
// Remove listen other than listen 80;
// Add index.php before index.html
// uncomment location ~ \.php$ block
// change FPM ver from 7.0 to 7.2
// uncomment location ~ /\.ht block
sudo nginx -t
sudo ln -s /etc/nginx/sites-enabled/midtest etc/nginx/sites-enabled/
sudo service nginx reload
// nginx failed to reload
sudo servie nginx stop
sudo service nginx start
// nginx failed to start
sudo unlink /etc/nginx/sites-available/default
sudo unlink /etc/nginx/sites-available/midtest
sudo ln -s /etc/nginx/sites-available/default /etc/nginx/sites-available
sudo service nginx start
// nginx failed to start
sudo unlink /etc/nginx/sites-available/default
// midtest and default are gone :(
// proceed re-installing nginx
sudo apt purge nginx
sudo apt install nginx start
// nginx failed to start



// CHANGE PC FRESH START


// Package Installation
sudo apt install nginx mariadb-server mariadb-client php7.2 php7.2-fpm
sudo apt-get update
sudo apt install nginx mariadb-server mariadb-client php7.2 php7.2-fpm
sudo service nginx start
sudo service mysql start
sudo mysql_secure_installation
curl -4 icanhazip.com
sudo service mysql status
// mariadb is running
sudo service nginx start
// nginx is running

// Nginx Server Setup
cd etc/nginx/sites-available
sudo cp default midtest
sudo nano midtest
// Remove listen other than listen 80;
// Add index.php before index.html
// uncomment location ~ \.php$ block
// THE PROBLEM WAS WE DIDN'T KEEP CGI COMMENTED
// change FPM ver from 7.0 to 7.2
// uncomment location ~ /\.ht block
sudo nginx -t
sudo ln -s /etc/nginx/sites-enabled/midtest etc/nginx/sites-enabled/
sudo service nginx reload
cd var/www/html
sudo nano info.php
