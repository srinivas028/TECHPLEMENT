# TECHPLEMENT
 # DEPLOYING WORDPRESS AND MYSQL IN A SINGLE EC2 INSTANCE
PREREQUISITES:
# aws account
# t2.micro

# STEPS 
1. Create a ec2 instance with specific name.
2. create a key pair and allow the *http* ,*https* traffic and finally take *t2.micro* size, then launch instance.
3. Then connect to instance and the type *sudo -i* for root user.
4. Install Apache server on Ubuntu
# *sudo apt install apache2*

5. Install php runtime and php mysql connector to run the apache2 and mysql
# *sudo apt install php libapache2-mod-php php-mysql*

6. Install MySQL server
# *sudo apt install mysql-server*

7. Login to MySQL server
# *sudo mysql -u root*

8. Change authentication plugin to mysql_native_password (change the password to something strong)
# *ALTER USER 'root'@'localhost' IDENTIFIED BY 'testpassword@123';*

9. Create a new database user for wordpress (change the password to something strong)
# *CREATE USER 'wp_user'@localhost IDENTIFIED BY 'testpassword@123';*

10. Create a database for wordpress
# *CREATE DATABASE wordpress;*

11. Grant all privilges on the database 'wp' to the newly created user
# *GRANT ALL PRIVILEGES ON wordpress.*TO 'wp_user'@localhost;*

12.then exit to the root user by 
# *exit;*

13. Now Download wordpress
# *wget https://wordpress.org/latest.tar.gz*

14. Unzip
# *tar -xvzf latest.tar.gz*

15. Move wordpress folder to apache document root
# *sudo mv wordpress/ /var/www/html*

16. Command to restart/reload apache server
# *sudo systemctl restart apache2*

17. Now access to the *public_ip* of ec2 instance and *public_ip/wordpress* to access to wordpress

18. Give the details of databases and user in the wordpress and then run installation by creating a file and copying the php text in the wordpress directory

19. That's it now we can access wordpress with our own database.
