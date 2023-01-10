# MySQL root password change

## In the MySQL command-line client, phpMyAdmin or any MySQL GUI:

### Way 1
```sql UPDATE mysql.user
SET authentication_string=PASSWORD('MyNewPass')
WHERE user='root';

FLUSH PRIVILEGES;

```

### Way 2
```sql 
# mysql -u root

mysql> USE mysql;
mysql> UPDATE user SET plugin='mysql_native_password' WHERE User='root';
mysql> set password for 'root'@'localhost' = PASSWORD('mySecretPassword'); 
mysql> FLUSH PRIVILEGES;
mysql> exit;

# service mysql restart

```sql 