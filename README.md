# MySQL Note

# Connect to mysql with usernane and password

```bash
mysql -u <username> -p
```

## List users with single line command
```bash
mysql -u root -p -e 'SELECT user,authentication_string,plugin,host FROM mysql.user';
```

[Users and Permissions](./UserGrants.md)
