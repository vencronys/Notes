# MariaDB Cheatsheet

## **Installation (Arch Linux)**
```sh
sudo pacman -S mariadb
```

## **Initialize and Start Database**
```sh
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
sudo systemctl start mariadb
sudo systemctl enable mariadb
```

## **Secure MariaDB Installation**
```sh
sudo mysql_secure_installation
```
Follow the prompts to:
- Set root password
- Remove anonymous users
- Disallow remote root login
- Remove test database

## **User and Database Management**
### Log into MariaDB
```sh
sudo mariadb
```
If you want to use `mariadb -u root -p` but get `ERROR 1698 (28000)`, see the section **Fixing Root Access Issues** below.

### Create a new user
```sql
CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'mypassword';
```

### Create a new database
```sql
CREATE DATABASE mydatabase;
```

### Grant privileges
```sql
GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser'@'localhost';
FLUSH PRIVILEGES;
```

## **Fixing Root Access Issues**
If you see `ERROR 1698 (28000): Access denied for user 'root'@'localhost'`, it means MariaDB is using **Unix socket authentication**, allowing only system users to log in as root without a password.

### **Fix 1: Use sudo to log in**
```sh
sudo mariadb
```

### **Fix 2: Change root to password-based authentication**
1. **Log in using sudo:**
   ```sh
   sudo mariadb
   ```

2. **Switch to the `mysql` database:**
   ```sql
   USE mysql;
   ```

3. **Update root authentication to password-based:**
   ```sql
   ALTER USER 'root'@'localhost' IDENTIFIED VIA mysql_native_password USING PASSWORD('your_secure_password');
   FLUSH PRIVILEGES;
   ```

4. **Exit and test:**
   ```sh
   mariadb -u root -p
   ```

### **Fix 3: Create an alternative admin user**
If you want to keep root restricted and use a different user:

1. **Log in using sudo:**
   ```sh
   sudo mariadb
   ```

2. **Create a new admin user:**
   ```sql
   CREATE USER 'admin'@'localhost' IDENTIFIED BY 'your_secure_password';
   GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
   FLUSH PRIVILEGES;
   ```

3. **Log in with the new admin user:**
   ```sh
   mariadb -u admin -p
   ```

## **Securing MariaDB Connections**
### Change password to use strong authentication
```sql
ALTER USER 'myuser'@'localhost' IDENTIFIED BY 'newpassword';
```

### Restrict remote access (only allow local connections)
Edit MariaDB configuration file:
```sh
sudo nvim /etc/my.cnf.d/server.cnf
```
Ensure `bind-address` is set to:
```
bind-address = 127.0.0.1
```
Restart MariaDB:
```sh
sudo systemctl restart mariadb
```

## **Connecting to MariaDB**
```sh
mariadb -u myuser -p mydatabase
```

## **Table Operations**
### Create a table
```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    role VARCHAR(50),
    salary DECIMAL(10,2)
);
```

### Insert data
```sql
INSERT INTO employees (name, role, salary) VALUES
('Alice', 'Software Engineer', 70000.00),
('Bob', 'Database Administrator', 80000.00);
```

### Select data
```sql
SELECT * FROM employees;
```

### Update data
```sql
UPDATE employees SET salary = 90000.00 WHERE name = 'Alice';
```

### Delete data
```sql
DELETE FROM employees WHERE name = 'Bob';
```

## **Foreign Keys and Constraints**
### Create a table with a foreign key
```sql
CREATE TABLE departments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    role VARCHAR(50),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(id) ON DELETE CASCADE
);
```

### Check constraints
```sql
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) CHECK (price > 0)
);
```

### Enforce unique constraints
```sql
ALTER TABLE employees ADD CONSTRAINT unique_name UNIQUE(name);
```

## **Advanced Queries**
### Joins
```sql
SELECT e.name, d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.id;
```

### Aggregation
```sql
SELECT role, AVG(salary) FROM employees GROUP BY role;
```

### Subqueries
```sql
SELECT name FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
```

### Indexing
```sql
CREATE INDEX idx_salary ON employees(salary);
```

### Transactions
```sql
START TRANSACTION;
UPDATE employees SET salary = salary + 5000;
ROLLBACK; -- Or COMMIT;
```

## **Backup and Restore**
### Backup a database
```sh
mariadb-dump -u myuser -p mydatabase > mydatabase.sql
```

### Restore a database
```sh
mariadb -u myuser -p mydatabase < mydatabase.sql
```

## **Performance Tuning**
### Analyze query execution
```sql
EXPLAIN ANALYZE SELECT * FROM employees;
```

### Optimize tables
```sql
OPTIMIZE TABLE employees;
```

## **GUI Tools (Optional)**
### Install DBeaver
```sh
sudo pacman -S dbeaver
```

### Install MySQL Workbench
```sh
sudo pacman -S mysql-workbench
```

