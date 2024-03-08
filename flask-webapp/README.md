# Simple Flask Web Application Manual Steps:

This is a simple web application using [Python Flask] and [MySQL] database. 
This is used in the demonstration of the development of Ansible Playbooks.
  
  Below are the steps required to get this working on a base Linux system.
  
  - Install all required dependencies
  - Install and Configure Database
  - Start Database Service
  - Install and Configure Web Server
  - Start Web Server
   
## 1. Install all required dependencies
  
  Python and its dependencies

    apt-get install -y python3 python3-setuptools python3-dev build-essential python3-pip python3-flask

   
## 2. Install and Configure Database
    
 Install MySQL database
    
    apt-get install -y mysql-server mysql-client python3-pymysql php-mysql python3-mysqldb

## 3. Start Database Service
  - Start the database service
    
        service mysql start

  - Create database and database users
        
        # mysql -u <username> -p
        
        mysql> CREATE DATABASE employee_db;
        mysql> CREATE USER 'db_user'@'localhost' IDENTIFIED BY 'Passw0rd';    
        mysql> GRANT ALL ON employee_db.* TO 'db_user'@'localhost';
        mysql> USE employee_db;
        mysql> CREATE TABLE employees (name VARCHAR(20));
        
  - Insert some test data
        
        mysql> INSERT INTO employees VALUES ('SHUBHAM');
    
## 4. Install and Configure Web Server

Install Python Flask dependency

    pip install flask
    pip install flask-mysql

- Copy app.py or download it from source repository
- Configure database credentials and parameters 

## 5. Start Web Server

Start web server

    FLASK_APP=/opt/app.py nohup flask run --host=0.0.0.0 &
    
## 6. Test

Open a browser and go to URL

    http://<IP>:5000                            => Welcome
    http://<IP>:5000/how%20are%20you            => I am good, how about you?
    http://<IP>:5000/read%20from%20database     => JOHN


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

# Simple Flask Web Application Setup using Ansible Steps:

This is a simple web application using [Python Flask] and [MySQL] database. 
This is used in the demonstration of the development of Ansible Playbooks.
  
  Below are the steps required to get this working on a base Linux system.
  
  - Clone flask-webapp repo to the Linux system
  - Change inventory.yml - Add accurate values of ansible_host & ansible_sudo_pass
  - Run ansible-playbook flask-app-deploy.yml
  
   
## 1. Run ansible-playbook flask-app-deploy.yml

    ansible-playbook flask-app-deploy.yml -i inventory.yml
    
## 2. Test

Open a browser and go to URL

    http://<IP>:5000                            => Welcome
    http://<IP>:5000/how%20are%20you            => I am good, how about you?
    http://<IP>:5000/read%20from%20database     => JOHN

### NOTE: After running ansible-playbook few manual steps are required to create table and insert values to employees table.
  
  - CREATE TABLE employees

        mysql> CREATE TABLE employees (name VARCHAR(20));

  - Insert values in employees TABLE
 
        mysql> INSERT INTO employees VALUES ('SHUBHAM');
