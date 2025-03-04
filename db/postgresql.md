# PostgreSQL Cheatsheet

## **Installation (Arch Linux)**
```sh
sudo pacman -S postgresql
```

## **Initialize and Start Database**
```sh
sudo -iu postgres initdb -D /var/lib/postgres/data
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

## **User and Database Management**
### Create a new user (role)
```sh
createuser --interactive
```
Or with a password:
```sql
CREATE ROLE myuser WITH LOGIN PASSWORD 'mypassword' SUPERUSER;
```

### Create a new database
```sh
createdb mydatabase
```
Or:
```sql
CREATE DATABASE mydatabase OWNER myuser;
```

### Grant privileges
```sql
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
```

## **Securing PostgreSQL Connections**
### Enable password authentication with scram-sha-256
Edit the authentication file:
```sh
sudo nvim /var/lib/postgres/data/pg_hba.conf
```
Change:
```
local   all   all   peer
```
to:
```
local   all   all   scram-sha-256
```
Restart PostgreSQL:
```sh
sudo systemctl restart postgresql
```

### Update user password to use SCRAM-SHA-256
```sql
ALTER ROLE myuser WITH ENCRYPTED PASSWORD 'mypassword';
```

### Restrict remote access
Edit `postgresql.conf`:
```sh
sudo nvim /var/lib/postgres/data/postgresql.conf
```
Find `listen_addresses` and set it to:
```
listen_addresses = 'localhost'
```
Restart PostgreSQL:
```sh
sudo systemctl restart postgresql
```

## **Connecting to PostgreSQL**
```sh
psql -U myuser -d mydatabase
```

### Switch database
```sql
\c mydatabase
```

## **Table Operations**
### Create a table
```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    role VARCHAR(50),
    salary NUMERIC
);
```

### Insert data
```sql
INSERT INTO employees (name, role, salary) VALUES
('Alice', 'Software Engineer', 70000),
('Bob', 'Database Administrator', 80000);
```

### Select data
```sql
SELECT * FROM employees;
```

### Update data
```sql
UPDATE employees SET salary = 90000 WHERE name = 'Alice';
```

### Delete data
```sql
DELETE FROM employees WHERE name = 'Bob';
```

## **Foreign Keys and Constraints**
### Create a table with a foreign key
```sql
CREATE TABLE departments (
    id SERIAL PRIMARY KEY,
    department_name VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    role VARCHAR(50),
    salary NUMERIC,
    department_id INT REFERENCES departments(id) ON DELETE CASCADE
);
```

### Check constraints
```sql
CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    price NUMERIC CHECK (price > 0)
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
BEGIN;
UPDATE employees SET salary = salary + 5000;
ROLLBACK; -- Or COMMIT;
```

## **Backup and Restore**
### Backup a database
```sh
pg_dump mydatabase > mydatabase.sql
```

### Restore a database
```sh
psql -U myuser -d mydatabase -f mydatabase.sql
```

## **Performance Tuning**
### Analyze query execution
```sql
EXPLAIN ANALYZE SELECT * FROM employees;
```

### Vacuum to optimize performance
```sh
vacuumdb --analyze mydatabase
```

## **GUI Tools (Optional)**
### Install DBeaver
```sh
sudo pacman -S dbeaver
```

### Install pgAdmin (Manual Install)
[https://www.pgadmin.org](https://www.pgadmin.org)
