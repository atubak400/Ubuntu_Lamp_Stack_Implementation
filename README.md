# **Ubuntu Lamp Stack Implementation on AWS**

## **What is a LAMP Stack**

A LAMP stack is a commonly used set of software components that together provide a platform for building and hosting dynamic websites and web applications. The name "LAMP" is an acronym for the four key components that make up the stack: Linux, Apache, MySQL, and PHP/Perl/Python (usually referred to as PHP).

## **Overview of each component of the LAMP Stack**

#### *Linux*
The operating system that serves as the foundation of the stack. It provides the environment for running the other components and managing hardware resources.

#### *Apache*
A popular open-source web server software that listens to incoming HTTP requests from clients (web browsers), processes those requests, and serves web content (HTML, CSS, JavaScript, etc.) back to the clients. It's responsible for handling the communication between the server and the client's browser.

#### *MySQL*
A widely used open-source relational database management system (RDBMS) that manages and stores structured data. MySQL is crucial for storing and retrieving data for web applications, making it possible to create dynamic websites that interact with databases.

#### *PHP/Perl/Python*
These are scripting languages used to develop dynamic web content and applications. In the context of the LAMP stack, PHP is the most common choice. PHP scripts are embedded within HTML and executed on the server side. They generate dynamic content that's sent to the client's browser as HTML, allowing for interactive and data-driven web applications.


# **The steps in our implementation process include**
a. Setting up and Connecting to ec2 Ubuntu Virtual Machine

b. Installing Apache

c. Installing MYSQL

d. Installing php

e. Enabling php on the website

---

---

## A. **Setting up and Connecting to ec2 Ubuntu Virtual Machine**

---

---

Step 1: Log in to aws and create an ubuntu ec2 instance. 

![Creating an ubuntu ec2 instance](./Images/1.png)

Instance Created!

![Instance Created](./Images/2.png)

---

---

Step 2: Connect to Ubuntu Instance using Instance Connect.

![Connecting to our Ubuntu Instance](./Images/3.png)

Connection Successful!

![Connection Successful](./Images/4.png)

---

---

## B. **Install Apache**

---

---

Step 3: Update the package repository by running `sudo apt update`

![sudo apt update](./Images/5.png)

---

---

Step 4: Install Apache by running `sudo apt install apache2`

![sudo apt install apache2](./Images/6.png)

---

---

Step 5: Verify Apache is running by running `sudo systemctl status apache2`.
If you see a green colored "active(running)", Apache successfully insstalled and started on port 80!.

![sudo systemctl status apache2](./Images/7.png)

---

---

Step 6: Open a web browser of your choice (Chrome recommended), navigate to `http://Public-IP-Address-of-ec2:80`

If you see the page below then your web server is correctly installed and accessible through the firewall.

![Apache home page](./Images/8.png)

---

---

## C. **Install MYSQL**

---

---

Step 7: Use apt to install mysql-server by running `sudo apt install mysql-server`

![sudo apt install mysql-server](./Images/9.png)

---

---


Step 8: Log in to mysql console by running `sudo mysql`

![sudo mysql](./Images/10.png)

---

---

Step 9: Set password for mysql root user by running `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';` and exit mysql shell by running `exit`

![sudo systemctl status apache2](./Images/11.png)

---

---

Step 10: Run the MySQL secure installation script to improve security `sudo mysql_secure_installation`

![sudo systemctl status apache2](./Images/12.png)

---

---

Step 11: Exit mysql shell by running `exit`

![sudo systemctl status apache2](./Images/13.png)

---

---

## D. **Install PHP**

---

---

Step 12: Install PHP and required modules by running `sudo apt install php libapache2-mod-php php-mysql`

![sudo apt install mysql-server](./Images/14.png)

---

---

Step 13: Confirm your php version by running `php -v`

![sudo mysql](./Images/15.png)

---

---

## E. **Enabling php on the website**

---

---

Step 14: To edit the dir.conf file and change the order in which the index.php file is listed, run `sudo nano /etc/apache2/mods-enabled/dir.conf` 

![sudo systemctl status apache2](./Images/16.png)

---

---

Step 15: Replace the code you find in dir.conf with this:

```apache
<IfModule mod_dir.c>
    # Change this:
    # DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
    # To this:
    DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```
Save and exit the nano editor

---

---

Step 17: Reload apache so that the changes can take effect by running `sudo systemctl reload apache2`

![sudo systemctl status apache2](./Images/18.png)

---

---

Step 18: Create and open a new file inside root your folder by running `sudo nano /var/www/projectlamp/index.php`

![sudo systemctl status apache2](./Images/19.png)

---

---

Step 19: Paste the following php code in the blank file

```php
<?php
phpinfo();
?> 
```
![sudo systemctl status apache2](./Images/20.png)
---

---

Step 20: Open it in browser using `http://localhost/index.php` or `http://yourserveripaddress/test.php` depending on what you have. Should see the image below:
![sudo systemctl status apache2](./Images/21.png)

---

---

Step 22: For security reasons remove the index.php file by running `sudo rm /var/www/projectlamp/index.php`

---

---

# Congratulations! You have successfully installed Apache, MySql and php on your server.

---

---




