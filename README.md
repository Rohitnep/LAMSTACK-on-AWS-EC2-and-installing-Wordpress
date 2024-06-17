# LAMSTACK-on-AWS-EC2-and-installing-WordPress

1 - create an instance of whatever OS you prefer, Ubuntu or linux. Then connect the instance through cmd or mac terminal. I am using ubuntu. For that go to your cmd or mac terminal. Then fire the cd downloads command to locate where the key pair is. Then fire command for connecting.
```
ssh -i “yourkeyname” username@publicipaddress
```
2 - after successfully connecting, first update the ubuntu. For that, fire the update command.
```
sudo apt-get update
```
3 - then fir the upgrade command.
```
sudo apt-get upgrade
```
4 - Now, first install apache. For that fire the installation command.
```
sudo apt-get install apache2
```
5 - then check the status if it's active or not.
```
sudo systemctl status apache2
```
6 - then enable it
```
sudo systemctl enable apache2
```
7 - then we are going to install mariadb. MariaDB is an open source and forever-free MySQL alternative that offers greater efficiency, enhanced database performance, and support for various data types through multiple storage engines. For installing mariadb, fire mariadb installation command.
```
sudo apt-get install mariadb-server mariadb-client
```
8 - after installing, start mariadb.
```
sudo systemctl start mariadb
```
9 - then enable mariadb.
```
sudo systemctl enable mariadb
```
10 - Now, we are going to install mysql. For that fire the installation command.
```
sudo mysql_secure_installation
```
11 - when installing, create a password for mariadb as proceeding. After creating the password click on y=>y=>y=>y and mariadb and mysql is installed.
12 - this is where you will change the password. Type y and hit enter.
13 - Write a new password and hit enter and again rewrite the password and hit enter.
14 - After this, again keep typing Y and hit enter.
15 - Now, restart mariadb.
```
sudo systemctl restart mariadb
```
16 - Now, we are going to install php.
```
sudo apt-get install php php-mysql php-gd php-cli php-common
```
17 - Now, we need wordpress.
```
sudo apt-get install wget unzip -y
```
18 - Now, second go to the official website of wordpress and copy the download link of wordpress then we are going to paste it in cmd.
```
sudo wget https://wordpress.org/latest.zip
```
19 - then unzip the link.
```
sudo unzip latest.zip
```
20 - Now move that file to the directory.
```
sudo mv wordpress/* /var/www/html/ 
```
21 - Now, change the ownership of that file.
```
sudo chown www-data:www-data -R /var/www/html/
```
22 - Now, go to the directory.
```
cd /var/www/html
```
23 - Now, delete the existing index.html file.
```
sudo rm -rf index.html
```
24 - Now, login to mysql.
```
mysql -u root -p
```
25 - first create a database.
```
create database databasename;
```
26 - Now, we create a user and create a password.
```
create user “username” identified by “password”;
```
27 - now give all privileges to the database.
```
grant all privileges databasename.* to “username”;
```
And lastly type **quit** and hit enter.

28 - copy the public ip address and paste it to the browser and hit enter. Wordpress page will be open. Select language and click continue.

29 - click on let's go.

30 - type the database name we created and username and password. Then hit submit.

31 - click on run the installation.

32 - add a title. Add new username, change the default password and type new password, then add gmail id and hit submit.

33 - after creating a profile, click on log in.

34 - add the created username and password and click on log in.

35 - welcome to wordpress.
