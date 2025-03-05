# SQL Server Express Cheatsheet

## **Installation (Arch Linux)**
SQL Server is officially supported on **Ubuntu-based distributions**, but you can install it on Arch using **AUR**:
```sh
yay -S mssql-server
```

## **Start and Enable SQL Server**
```sh
sudo systemctl start mssql-server
sudo systemctl enable mssql-server
```

## **Run Initial Setup**
```sh
sudo /opt/mssql/bin/mssql-conf setup
```
Follow the prompts to:
- Accept the license
- Choose the edition (Select **Express** for free version)
- Set a strong **SA (System Admin) password**

## **Check Service Status**
```sh
systemctl status mssql-server
```

## **Install SQL Server Command-Line Tools**
```sh
yay -S mssql-tools
```

## **Connect to SQL Server**
```sh
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'your_password' -C
```

## **Create a New Database**
```sql
CREATE DATABASE mydatabase;
GO
```

## **Create a New User and Grant Permissions**
```sql
CREATE LOGIN myuser WITH PASSWORD = 'mypassword';
CREATE USER myuser FOR LOGIN myuser;
ALTER ROLE db_owner ADD MEMBER myuser;
GO
```

## **Security Hardening**
- **Force SSL connections**
  ```sh
  sudo /opt/mssql/bin/mssql-conf set network.tls 1.2
  sudo systemctl restart mssql-server
  ```
- **Change SA password policy** (Enforce strong passwords)
  ```sql
  ALTER LOGIN SA ENABLE;
  ALTER LOGIN SA WITH PASSWORD = 'YourNewSecurePassword';
  ```
- **Restrict remote access**
  ```sh
  sudo /opt/mssql/bin/mssql-conf set network.ipaddress 127.0.0.1
  sudo systemctl restart mssql-server
  ```

## **Basic SQL Server Queries**
### Select Database
```sql
USE mydatabase;
GO
```
### Create a Table
```sql
CREATE TABLE employees (
    id INT IDENTITY PRIMARY KEY,
    name NVARCHAR(100),
    role NVARCHAR(50),
    salary DECIMAL(10,2)
);
GO
```
### Insert Data
```sql
INSERT INTO employees (name, role, salary) VALUES
('Alice', 'Software Engineer', 70000.00),
('Bob', 'DBA', 80000.00);
GO
```
### Retrieve Data
```sql
SELECT * FROM employees;
GO
```

## **Foreign Keys & Constraints**
```sql
CREATE TABLE departments (
    id INT IDENTITY PRIMARY KEY,
    department_name NVARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE employees (
    id INT IDENTITY PRIMARY KEY,
    name NVARCHAR(100),
    role NVARCHAR(50),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(id) ON DELETE CASCADE
);
GO
```

## **Backup & Restore**
### Backup Database
```sql
BACKUP DATABASE mydatabase TO DISK = '/var/opt/mssql/backups/mydatabase.bak';
GO
```
### Restore Database
```sql
RESTORE DATABASE mydatabase FROM DISK = '/var/opt/mssql/backups/mydatabase.bak' WITH REPLACE;
GO
```

This guide provides a full setup for SQL Server Express on Arch Linux, including security configurations and essential SQL operations. Let me know if you need further refinements!

