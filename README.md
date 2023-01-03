# ubuntulemp
Notes on LEMP stacked on ubuntuless. How to's, etc.

## Nginx
sudo apt install nginx

#test with curl, output is html source

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

Test this box with different PHP frameworks and applications. Happy Provisioning!


## Supplementary references

Learn to manage multiple domains/projects at the link below:

(https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-22-04)
