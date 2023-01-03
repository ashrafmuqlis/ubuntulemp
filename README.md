# ubuntulemp
Notes on LEMP stacked on ubuntuless. How to's, etc.

## Nginx
sudo apt install nginx

#test with curl, output is html page

curl http://localhost or curl http://vaagrant-vm-ip

## MySQL Server
  
sudo apt install mysql-server

sudo mysql 

#set mysql root password to Mysqlroot123!

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Mysqlroot123!';

exit;

## PHP Library

sudo apt install php libapache2-mod-php php-mysql

#test php engine
  
php -v

## Create a test project/site
sudo mkdir /var/www/newdomain

sudo chown -R $USER:$USER /var/www/newdomain

## Configure newdomain
sudo nano /etc/nginx/sites-available/newdomain

```
server { listen 80; server_name newdomain www.newdomain; root /var/www/newdomain; index index.html index.htm index.php;
    location / { try_files $uri $uri/ =404; }
    location ~ \.php$ { include snippets/fastcgi-php.conf; fastcgi_pass unix:/var/run/php/php8.1-fpm.sock; }
    location ~ /\.ht { deny all; } }
```
    
## Configure hard links
sudo ln -s /etc/nginx/sites-available/newdomain /etc/nginx/sites-enabled/

## Disable the default apache2 site (~/www/html)
sudo unlink /etc/nginx/sites-enabled/default

## Validate Nginx configuration
sudo nginx -t

## Restart nginx service
sudo systemctl reload nginx

## Create an index.html in newdomain
nano /var/www/newdomain/index.html

```
<html>  <head>    <title>newdomain website</title> </head> 
<body> <h1>Hello World!</h1>
<p>This is the landing page of <strong>newdomain</strong>.</p>
</body>
</html>
```
  
#test with curl or browser, output is html page

curl http://localhost or curl http://vaagrant-vm-ip

Test this box with different PHP frameworks and applications. Happy Provisioning!


## Supplementary references

Learn to manage multiple domains/projects at the link below:

(https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-22-04)
