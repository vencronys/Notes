# Initializing a php project, the easy way

# The server

Withing the root of your peoject, run:

```bash
sudo php --server localhost:8080 --docroot  .
```

# Database connectivity

> [!sample]
> ```php
// Database connection settings
$host = '127.0.0.1';
$user = 'LOGIN';
$password = 'PASSWORD';
$dbname = 'DB_NAME';
// Create connection
$conn = new mysqli($host, $user, $password, $dbname);
// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully to MariaDB!";
> ```
