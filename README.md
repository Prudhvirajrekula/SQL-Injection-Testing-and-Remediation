# SQL Injection Testing and Remediation

This project demonstrates SQL Injection vulnerabilities and how to prevent them using prepared statements.

## Prerequisites
1. **Download & Install XAMPP** (for PHP & MySQL)
   - [Download XAMPP](https://www.apachefriends.org/download.html)
   - Install and start `Apache` and `MySQL` in the XAMPP Control Panel.

2. **Create a MySQL Database**
   - Open `phpMyAdmin` by visiting: `http://localhost/phpmyadmin/`
   - Create a new database: `testdb`
   - Run the following SQL query to create a `users` table:
     ```sql
     CREATE TABLE users (
         id INT AUTO_INCREMENT PRIMARY KEY,
         username VARCHAR(50) NOT NULL,
         password VARCHAR(50) NOT NULL
     );
     ```
   - Insert test users:
     ```sql
     INSERT INTO users (username, password) VALUES ('admin', 'admin123');
     INSERT INTO users (username, password) VALUES ('test', 'test123');
     ```

## Running the Project
1. **Save the Source Code**
   - Create a new folder inside `C:\xampp\htdocs\` (e.g., `sql_injection`)
   - Save the provided PHP files in this folder.

2. **Start XAMPP Services**
   - Open XAMPP Control Panel and start `Apache` and `MySQL`

3. **Access the Web Application**
   - Open a browser and go to: `http://localhost/sql_injection/`
   - Test both vulnerable and secure versions.

## Demonstrating SQL Injection
- In the vulnerable version, enter the following input:
  - **Username:** `admin' --`
  - **Password:** `anything`
  - This will log you in without knowing the password.

## Preventing SQL Injection
- Use the secure version with **prepared statements** to prevent attacks.
