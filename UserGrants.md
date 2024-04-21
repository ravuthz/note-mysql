# Connect to mysql with user root and password

```bash
mysql -u root -p
# mysql>
# mysql -u adminz -p
```

## Create User

```bash
## Create user with password 123123
# mysql> CREATE USER 'username'@'host' IDENTIFIED WITH authentication_plugin BY 'password';
CREATE USER 'admin'@'localhost' IDENTIFIED BY '123123'; # use default authentication_plugin
CREATE USER 'adminz'@'%' IDENTIFIED WITH mysql_native_password BY '123123';

## Update user with password 123123 using mysql_native_password plugin
# mysql> ALTER USER 'username'@'host' IDENTIFIED WITH authentication_plugin BY 'password';
ALTER USER 'admin'@'localhost' IDENTIFIED WITH mysql_native_password BY '123123';
ALTER USER 'adminz'@'%' IDENTIFIED WITH mysql_native_password BY '123123';
```

## Drop User

```bash
# mysql> DROP USER 'username'@'localhost';
DROP USER 'admin'@'localhost';
```

## Show Granted Permissions

```bash
# mysql> SHOW GRANTS FOR 'username'@'host';
SHOW GRANTS FOR 'adminz'@'%';

```

## Granting User Permissions

```bash
# mysql> GRANT PRIVILEGE ON database.table TO 'username'@'host';
GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'adminz'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

## Revoing User Permissions

```bash
# mysql> REVOKE type_of_permission ON database_name.table_name FROM 'username'@'host';
REVOKE DROP on *.* FROM 'adminz'@'%';
```
