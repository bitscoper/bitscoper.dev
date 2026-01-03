---
date: "2022-08-15T20:45:00+00:00"
title: "How to Grant Remote Login Privilege to a MariaDB User Account"
---

**Previous:** [How To Enable Remote Access To MariaDB Database Server On AlmaLinux 8](<https://bitscoper.dev/posts/how-to-enable-remote-access-to-mariadb-database-server-on-almalinux-8>)

---

Suppose we want to grant remote login privilege to the **_root_** user from **any** IP address or hostname. The _root_ user’s password is **asDFgh12345**.

---

**Granting remote login privilege to the _root_ user is a bad practice.**

---

### a) Generating Hashed Password

First, generate the hashed password for the user. Execute the following SQL statement:

`SELECT PASSWORD("asDFgh12345");`

Copy the result, which may look similar to the following string:

```text
*E459E5F12492FC860EDCF3739D82506B3BED1C79
```

### b) Making Entry

Grant the privilege by executing the following SQL statement:

`GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY PASSWORD '*E459E5F12492FC860EDCF3739D82506B3BED1C79' WITH GRANT OPTION;`

The wildcard **%** means **all IP addresses**, including **localhost**.

### c) Checking for Duplicate Entries

Check for duplicate entries by executing the following SQL statement:

`SELECT user, authentication_string, plugin, host FROM mysql.user;`

The **mysql.user** table should contain only one entry per user. If you find another entry for the same user, you must delete it.

### d) Reloading Grant Tables

Reload the grant tables by executing the following SQL statement:

`FLUSH PRIVILEGES;`

---

### Documentation

- <https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/>
